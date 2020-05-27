---
title: 학습 가능한 분류자 시작하기(미리 보기)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 365 trainable 분류자는 긍정적이 고 부정적 샘플을 확인 하 여 다양 한 유형의 콘텐츠를 인식할 수 있도록 교육을 제공 하는 도구입니다. 일단 분류자가 학습 되 면 결과가 정확 함을 확인할 수 있습니다. 그런 다음이를 사용 하 여 조직의 콘텐츠를 검색 하 고이를 분류 하 여 보존 또는 민감도 레이블을 적용 하거나 DLP (데이터 손실 방지) 또는 보존 정책에 포함 합니다.
ms.openlocfilehash: de52c8c7f96d2d3c0383f27b17bcc5162bb662c5
ms.sourcegitcommit: 87eff6e8a08cec3cb0464a3b765434717584a4a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/26/2020
ms.locfileid: "44371466"
---
# <a name="getting-started-with-trainable-classifiers-preview"></a><span data-ttu-id="dbf32-105">학습 가능한 분류자 시작하기(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="dbf32-105">Getting started with trainable classifiers (preview)</span></span>

<span data-ttu-id="dbf32-106">콘텐츠를 보호 하 고 적절 하 게 레이블을 지정 하 여 정보 보호 규칙의 시작 위치를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbf32-106">Classifying and labeling content so it can be protected and handled properly is the starting place for the information protection discipline.</span></span> <span data-ttu-id="dbf32-107">Microsoft 365에는 세 가지 방법으로 콘텐츠를 분류할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbf32-107">Microsoft 365 has three ways to classify content.</span></span>

## <a name="manually"></a><span data-ttu-id="dbf32-108">수동으로</span><span class="sxs-lookup"><span data-stu-id="dbf32-108">Manually</span></span>

<span data-ttu-id="dbf32-109">이 방법을 사용 하려면 사용자의 판단 및 조치가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbf32-109">This method requires human judgment and action.</span></span> <span data-ttu-id="dbf32-110">관리자는 기존 레이블과 중요 한 정보 유형을 사용 하거나 직접 만들어 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbf32-110">An admin may either use the pre-existing labels and sensitive information types or create their own and then publish them.</span></span> <span data-ttu-id="dbf32-111">사용자와 관리자는 콘텐츠를 발견 하는 콘텐츠에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbf32-111">Users and admins apply them to content as they encounter it.</span></span> <span data-ttu-id="dbf32-112">그런 다음 콘텐츠를 보호 하 고 해당 처리를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbf32-112">You can then protect the content and manage its disposition.</span></span>

## <a name="automated-pattern-matching"></a><span data-ttu-id="dbf32-113">자동화 된 패턴 일치</span><span class="sxs-lookup"><span data-stu-id="dbf32-113">Automated pattern matching</span></span>

<span data-ttu-id="dbf32-114">이 분류 메커니즘 범주에는 다음을 통한 콘텐츠 찾기가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbf32-114">This category of classification mechanisms includes finding content by:</span></span>

- <span data-ttu-id="dbf32-115">키워드 또는 메타 데이터 값 (키워드 쿼리 언어)</span><span class="sxs-lookup"><span data-stu-id="dbf32-115">Keywords or metadata values (keyword query language).</span></span>
- <span data-ttu-id="dbf32-116">공유 보안, 신용 카드 또는 은행 계좌 번호와 같은 중요 한 정보 [(중요 한 정보 유형 엔터티 정의)](sensitive-information-type-entity-definitions.md)를 이전에 식별 한 패턴으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbf32-116">Using previously identified patterns of sensitive information like social security, credit card or bank account numbers [(Sensitive information type entity definitions)](sensitive-information-type-entity-definitions.md).</span></span>
- <span data-ttu-id="dbf32-117">서식 파일의 변형 [(문서 손가락 인쇄)](document-fingerprinting.md)으로 인해 항목을 인식 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbf32-117">Recognizing an item because it's a variation on a template [(document finger printing)](document-fingerprinting.md).</span></span>
- <span data-ttu-id="dbf32-118">정확한 문자열 [(정확한 데이터 일치)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbf32-118">Using the presence of exact strings [(exact data match)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

<span data-ttu-id="dbf32-119">그런 다음 민감도 및 보존 레이블을 자동으로 적용 하 여 [DLP (데이터 손실 방지)](data-loss-prevention-policies.md) 및 [보존 정책](retention-policies.md)에서 콘텐츠를 사용할 수 있도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbf32-119">Sensitivity and retention labels can then be automatically applied to make the content available for use in [data loss prevention (DLP)](data-loss-prevention-policies.md) and [retention policies](retention-policies.md).</span></span>

## <a name="trainable-classifiers"></a><span data-ttu-id="dbf32-120">Trainable 분류자</span><span class="sxs-lookup"><span data-stu-id="dbf32-120">Trainable classifiers</span></span>

<span data-ttu-id="dbf32-121">이 분류 방법은 수동 또는 자동 패턴 일치 방법으로 쉽게 식별할 수 없는 콘텐츠에 특히 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbf32-121">This classification method is particularly well suited to content that isn't easily identified by either the manual or automated pattern matching methods.</span></span> <span data-ttu-id="dbf32-122">이 분류 방법은 항목에 있는 요소 (패턴 일치)가 아니라 항목을 기준으로 항목을 식별 하는 분류자를 교육 하는 방법에 대해 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbf32-122">This method of classification is more about training a classifier to identify an item based on what the item is, not by elements that are in the item (pattern matching).</span></span> <span data-ttu-id="dbf32-123">분류자는 분류에 관심이 있는 콘텐츠의 수백 가지 예를 검토 하 여 콘텐츠 형식을 식별 하는 방법을 학습 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbf32-123">A classifier learns how to identify a type of content by looking at hundreds of examples of the content you're interested in classifying.</span></span> <span data-ttu-id="dbf32-124">먼저 범주에서 명확 하 게 보여 주는 예제를 공급 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbf32-124">You start by feeding it examples that are definitely in the category.</span></span> <span data-ttu-id="dbf32-125">이를 처리 하 고 나면 일치 및 일치 하지 않는 예제를 모두 함께 제공 하 여 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbf32-125">Once it processes those, you test it by giving it a mix of both matching and non-matching examples.</span></span> <span data-ttu-id="dbf32-126">그런 다음 분류자는 지정 된 항목이 작성 중인 범주에 속하는지 여부에 따라 예측을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbf32-126">The classifier then makes predictions as to whether any given item falls into the category you're building.</span></span> <span data-ttu-id="dbf32-127">그런 다음 결과를 확인 하 여 정확도를 높일 수 있도록 긍정, 음수, 가양성 및 거짓 네거티브를 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbf32-127">You then confirm its results, sorting out the positives, negatives, false positives, and false negatives to help increase the accuracy of its predictions.</span></span> <span data-ttu-id="dbf32-128">숙련 된 분류자를 게시 하면 SharePoint Online, Exchange 및 OneDrive와 같은 위치에 있는 항목을 통해 정렬 되며 콘텐츠를 분류 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbf32-128">When you publish the trained classifier, it sorts through items in locations like SharePoint Online, Exchange, and OneDrive, and classifies the content.</span></span>

### <a name="where-you-can-use-trainable-classifiers"></a><span data-ttu-id="dbf32-129">Trainable 분류자를 사용할 수 있는 위치</span><span class="sxs-lookup"><span data-stu-id="dbf32-129">Where you can use trainable classifiers</span></span>
<span data-ttu-id="dbf32-130">기본 제공 분류자와 trainable 분류자는 모두 조건 및 [통신 준수](communication-compliance-configure.md)를 [기반으로 하는 자동 적용 보존 레이블 정책의](labels.md#applying-a-retention-label-automatically-based-on-conditions) 조건으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbf32-130">Both built-in classifiers and trainable classifiers are available as a condition for [auto-apply retention label policy based on a condition](labels.md#applying-a-retention-label-automatically-based-on-conditions) and [communication compliance](communication-compliance-configure.md).</span></span> 

<span data-ttu-id="dbf32-131">민감도 레이블은 기본 제공 및 빌드 자체 분류자를 조건으로 사용할 수 있으며, [자동으로 콘텐츠에 민감도 레이블 적용](apply-sensitivity-label-automatically.md)및 [Office 앱에 대 한 자동 레이블](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)지정을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dbf32-131">Sensitivity labels can use built-in and build-your-own classifiers as conditions, see [Apply a sensitivity label to content automatically](apply-sensitivity-label-automatically.md), and [auto-labeling for Office apps](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dbf32-132">Trainable 분류자는 암호화 되지 않고 영어로 있는 항목에 대해서만 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbf32-132">Trainable classifiers only work with items that are not encrypted and are in English.</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="dbf32-133">라이선스 요구 사항</span><span class="sxs-lookup"><span data-stu-id="dbf32-133">Licensing requirements</span></span>

<span data-ttu-id="dbf32-134">Trainable 분류자는 Microsoft 365 E5 또는 E5 규정 준수 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="dbf32-134">Trainable classifiers are a Microsoft 365 E5, or E5 Compliance feature.</span></span> <span data-ttu-id="dbf32-135">이러한 구독 중 하나를 사용 하 여이를 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbf32-135">You must have one of these subscriptions to make use of them.</span></span>

### <a name="pre-requisites"></a><span data-ttu-id="dbf32-136">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="dbf32-136">Pre-requisites</span></span>

<span data-ttu-id="dbf32-137">UI에서 trainable 분류자에 액세스 하려면:</span><span class="sxs-lookup"><span data-stu-id="dbf32-137">To access trainable classifiers in the UI:</span></span> 
- <span data-ttu-id="dbf32-138">전역 관리자가 테 넌 트를 옵트인 해야 함</span><span class="sxs-lookup"><span data-stu-id="dbf32-138">the Global admin needs to opt in for the tenant</span></span>
- <span data-ttu-id="dbf32-139">분류자를 교육 하려면 준수 관리자 역할 또는 준수 데이터 관리자가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbf32-139">Compliance admin role or Compliance Data Administrator is required to train a classifier</span></span>

<span data-ttu-id="dbf32-140">다음 시나리오에서 trainable 분류자를 사용 하려면 이러한 사용 권한이 있는 계정이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbf32-140">You'll need accounts with these permissions to use trainable classifiers in these scenarios:</span></span>

- <span data-ttu-id="dbf32-141">보존 레이블 정책 시나리오: RecordManagement and 보존 관리 역할</span><span class="sxs-lookup"><span data-stu-id="dbf32-141">Retention label policy scenario: RecordManagement and Retention Management roles</span></span> 
- <span data-ttu-id="dbf32-142">민감도 레이블 정책 시나리오: 보안 관리자, 준수 관리자, 준수 데이터 관리자</span><span class="sxs-lookup"><span data-stu-id="dbf32-142">Sensitivity label policy scenario: Security Administrator, Compliance Administrator, Compliance Data Administrator</span></span>
- <span data-ttu-id="dbf32-143">통신 준수 정책 시나리오: 참가자 위험 관리 관리자, 관리 검토 관리자</span><span class="sxs-lookup"><span data-stu-id="dbf32-143">Communication compliance policy scenario: Insider Risk Management Admin, Supervisory Review Administrator</span></span> 

## <a name="types-of-classifiers"></a><span data-ttu-id="dbf32-144">분류자 유형</span><span class="sxs-lookup"><span data-stu-id="dbf32-144">Types of classifiers</span></span>

<span data-ttu-id="dbf32-145">기본 제공 되는 분류자와 trainable 분류자는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="dbf32-145">There are built-in classifiers and trainable classifiers.</span></span> <span data-ttu-id="dbf32-146">Trainable 분류자를 publishable 상태로 가져오면 훈련에 시간을 투자 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbf32-146">Getting a trainable classifier to a publishable state requires a time investment to train it.</span></span> <span data-ttu-id="dbf32-147">분류자 사용을 시작 하는 데 도움이 되도록 Microsoft 365에 몇 가지 기본 제공 분류자가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbf32-147">To help you get started using classifiers, Microsoft 365 comes with a few built-in classifiers.</span></span>

> [!NOTE]
> <span data-ttu-id="dbf32-148">분류 및 레이블 지정 워크플로에 기본 제공 분류자를 사용 하기 전에 분류 예측이 예상과 맞는지 확인 하기 위해 범주에 적합 한 조직의 콘텐츠 샘플에 대해 테스트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbf32-148">Before using any built-in classifier in your classification and labeling workflow, you should test it against a sample of your organizations content that you feel fits the category to verify that its classification predictions meet your expectations.</span></span>

### <a name="understanding-built-in-classifiers"></a><span data-ttu-id="dbf32-149">기본 제공 분류자 이해</span><span class="sxs-lookup"><span data-stu-id="dbf32-149">Understanding built-in classifiers</span></span>

<span data-ttu-id="dbf32-150">Microsoft 365에는 다음과 같이 권장 되는 5 가지 기본 제공 분류자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbf32-150">Microsoft 365 comes with five recommended built-in classifiers:</span></span>

> [!CAUTION]
> <span data-ttu-id="dbf32-151">당사는 **비속어** 기본 제공 분류자가 많은 수의 가양성을 생성하였기 에 그 사용을 중단하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbf32-151">We are deprecating the **Offensive Language** built-in classifier because it has been producing a high number of false positives.</span></span> <span data-ttu-id="dbf32-152">이 도구를 사용 하지 않고 현재 사용 중인 경우 비즈니스 프로세스를 외부에서 이동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbf32-152">Don't use it and if you are currently using it, you should move your business processes off of it.</span></span> <span data-ttu-id="dbf32-153">**위협**, **불경**및 **Harassment** 기본 제공 분류자를 대신 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="dbf32-153">We recommend using the **Threat**, **Profanity**, and **Harassment** built-in classifiers instead.</span></span>

- <span data-ttu-id="dbf32-154">**다시 시작**: 지원자 개인, 교육, 전문가 자격, 작업 환경 및 기타 개인 식별 정보에 대 한 텍스트 계정인 항목을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbf32-154">**Resumes**: detects items that are textual accounts of an applicant's personal, educational, professional qualifications, work experience, and other personally identifying information</span></span>
- <span data-ttu-id="dbf32-155">**소스 코드**: GitHub에서 상위 25 용으로 사용 되는 컴퓨터 프로그래밍 언어에 작성 된 지침 및 문 집합이 포함 되어 있는 항목을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbf32-155">**Source Code**: detects items that contain a set of instructions and statements written in the top 25 used computer programming languages on GitHub</span></span>

  |<span data-ttu-id="dbf32-156">언어 이름</span><span class="sxs-lookup"><span data-stu-id="dbf32-156">language name</span></span>|||||
  |---------|---------|---------|---------|---------|
  |<span data-ttu-id="dbf32-157">ActionScript</span><span class="sxs-lookup"><span data-stu-id="dbf32-157">ActionScript</span></span>|<span data-ttu-id="dbf32-158">C</span><span class="sxs-lookup"><span data-stu-id="dbf32-158">C</span></span>        |<span data-ttu-id="dbf32-159">& #</span><span class="sxs-lookup"><span data-stu-id="dbf32-159">C#</span></span>       |<span data-ttu-id="dbf32-160">C + +</span><span class="sxs-lookup"><span data-stu-id="dbf32-160">C++</span></span>     |<span data-ttu-id="dbf32-161">Clojure</span><span class="sxs-lookup"><span data-stu-id="dbf32-161">Clojure</span></span>  |
  |<span data-ttu-id="dbf32-162">CoffeeScript</span><span class="sxs-lookup"><span data-stu-id="dbf32-162">CoffeeScript</span></span>|<span data-ttu-id="dbf32-163">시트</span><span class="sxs-lookup"><span data-stu-id="dbf32-163">CSS</span></span>     |<span data-ttu-id="dbf32-164">갈</span><span class="sxs-lookup"><span data-stu-id="dbf32-164">Go</span></span>       |<span data-ttu-id="dbf32-165">Haskell</span><span class="sxs-lookup"><span data-stu-id="dbf32-165">Haskell</span></span> |<span data-ttu-id="dbf32-166">HTML</span><span class="sxs-lookup"><span data-stu-id="dbf32-166">HTML</span></span>     |
  |<span data-ttu-id="dbf32-167">Java</span><span class="sxs-lookup"><span data-stu-id="dbf32-167">Java</span></span>     |<span data-ttu-id="dbf32-168">JavaScript</span><span class="sxs-lookup"><span data-stu-id="dbf32-168">JavaScript</span></span>|<span data-ttu-id="dbf32-169">Lua</span><span class="sxs-lookup"><span data-stu-id="dbf32-169">Lua</span></span>      |<span data-ttu-id="dbf32-170">MATLAB</span><span class="sxs-lookup"><span data-stu-id="dbf32-170">MATLAB</span></span>   |<span data-ttu-id="dbf32-171">목표-C</span><span class="sxs-lookup"><span data-stu-id="dbf32-171">Objective-C</span></span>|
  |<span data-ttu-id="dbf32-172">Perl</span><span class="sxs-lookup"><span data-stu-id="dbf32-172">Perl</span></span>     |<span data-ttu-id="dbf32-173">PHP</span><span class="sxs-lookup"><span data-stu-id="dbf32-173">PHP</span></span>      |<span data-ttu-id="dbf32-174">Python</span><span class="sxs-lookup"><span data-stu-id="dbf32-174">Python</span></span>   |<span data-ttu-id="dbf32-175">이력서</span><span class="sxs-lookup"><span data-stu-id="dbf32-175">R</span></span>        |<span data-ttu-id="dbf32-176">Ruby</span><span class="sxs-lookup"><span data-stu-id="dbf32-176">Ruby</span></span>     |
  |<span data-ttu-id="dbf32-177">Scala</span><span class="sxs-lookup"><span data-stu-id="dbf32-177">Scala</span></span>    |<span data-ttu-id="dbf32-178">셸</span><span class="sxs-lookup"><span data-stu-id="dbf32-178">Shell</span></span>    |<span data-ttu-id="dbf32-179">Swift</span><span class="sxs-lookup"><span data-stu-id="dbf32-179">Swift</span></span>    |<span data-ttu-id="dbf32-180">Tex</span><span class="sxs-lookup"><span data-stu-id="dbf32-180">Tex</span></span>      |<span data-ttu-id="dbf32-181">Vim 스크립트</span><span class="sxs-lookup"><span data-stu-id="dbf32-181">Vim Script</span></span>|

> [!NOTE]
> <span data-ttu-id="dbf32-182">소스 코드는 대량의 텍스트가 소스 코드 인지 검색할 수 있도록 교육을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="dbf32-182">Source Code is trained to detect when the bulk of the text is source code.</span></span> <span data-ttu-id="dbf32-183">일반 텍스트와 섞여 있는 소스 코드 텍스트는 검색 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dbf32-183">It does not detect source code text that is interspersed with plain text.</span></span>

- <span data-ttu-id="dbf32-184">**Harassment**: 레이스, ethnicity, religion, 국립 근원, 성별, 성적 방향, 연령, 장애 등의 특성을 기반으로 하 여 한 명 이상의 개인이 대상으로 하는 공격적인 언어 텍스트 항목의 특정 범주를 감지 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbf32-184">**Harassment**: detects a specific category of offensive language text items related to offensive conduct targeting one or multiple individuals based on the following traits: race, ethnicity, religion, national origin, gender, sexual orientation, age, disability</span></span>
- <span data-ttu-id="dbf32-185">**불경**: 대부분의 사용자에 게 embarrass 하는 식이 포함 된 비속어 (공격적인 언어) 텍스트 항목의 특정 범주를 감지 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbf32-185">**Profanity**: detects a specific category of offensive language text items that contain expressions that embarrass most people</span></span>
- <span data-ttu-id="dbf32-186">**위협**: 사용자 또는 속성에 대 한 폭력을 커밋하거나 물리적으로 피해를 주거나 위험에 관련 된 비속어 텍스트 항목의 특정 범주를 감지 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbf32-186">**Threat**: detects a specific category of offensive language text items related to threats to commit violence or do physical harm or damage to a person or property</span></span>

<span data-ttu-id="dbf32-187">이러한 정보는의 상태를 포함 하는 **Microsoft 365 준수 센터**  >  **데이터 분류 (preview)**  >  **Trainable 분류자** 보기에 표시 `Ready to use` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbf32-187">These appear in the **Microsoft 365 compliance center** > **Data classification (preview)** > **Trainable classifiers** view with the status of `Ready to use`.</span></span>

![분류자-사용할 수 있는 분류자](../media/classifiers-ready-to-use-classifiers.png)

> [!IMPORTANT]
> <span data-ttu-id="dbf32-189">비속어, harassment, 비속어 및 threat 분류자는 검색 가능한 텍스트만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbf32-189">Please note that the offensive language, harassment, profanity, and threat classifiers only work with searchable text are not exhaustive or complete.</span></span>  <span data-ttu-id="dbf32-190">추가적으로, 언어 및 문화 표준이 지속적으로 변경 되 고 이러한 현실에 따라 Microsoft는 이러한 분류자를 업데이트할 수 있는 권리를 보유 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbf32-190">Further, language and cultural standards continually change, and in light of these realities, Microsoft reserves the right to update these classifiers in its discretion.</span></span> <span data-ttu-id="dbf32-191">이 분류자는 사용 중인 공격적인 및 기타 언어를 모니터링 하는 데 도움이 될 수 있지만, 이러한 언어의 결과를 해결 하는 것이 아니므로 조직의 해당 언어 사용에 대 한 다양 한 모니터링 또는 대응 수단을 제공 하기 위한 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="dbf32-191">While the classifiers may assist your organization in monitoring offensive and other language used, the classifiers do not address consequences of such language and are not intended to provide your organization's sole means of monitoring or responding to the use of such language.</span></span> <span data-ttu-id="dbf32-192">Microsoft 또는 해당 자회사가 아닌 조직은 미리 훈련 된 분류자로 식별 되는 콘텐츠의 모니터링, 적용, 차단, 제거 및 보존과 관련 된 모든 결정을 계속 담당 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbf32-192">Your organization, and not Microsoft or its subsidiaries, remains responsible for all decisions related to monitoring, enforcement, blocking, removal and retention of any content identified by a pre-trained classifier.</span></span>

#### <a name="process-flow-for-using-built-in-classifiers"></a><span data-ttu-id="dbf32-193">기본 제공 분류자 사용을 위한 프로세스 흐름</span><span class="sxs-lookup"><span data-stu-id="dbf32-193">Process flow for using built-in classifiers</span></span>

<span data-ttu-id="dbf32-194">기본 제공 분류자는 교육을 받을 필요가 없지만 준수 솔루션에서 사용 하기 전에 필요한 콘텐츠 유형을 확인할 필요가 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbf32-194">Built-in classifiers don't need to be trained, but you do need to confirm that they will identify the types of content that you need them to before you use them in compliance solutions.</span></span> <span data-ttu-id="dbf32-195">미리 훈련 된 분류자를 테스트 하려면이 흐름을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="dbf32-195">Testing a pre-trained classifier follows this flow.</span></span>

![미리 훈련 된 분류자를 테스트 하는 프로세스 흐름](../media/classifier-pre-trained-classifier-flow.png)

### <a name="understanding-trainable-classifiers"></a><span data-ttu-id="dbf32-197">Trainable 분류자 이해</span><span class="sxs-lookup"><span data-stu-id="dbf32-197">Understanding trainable classifiers</span></span>

<span data-ttu-id="dbf32-198">기본 제공 분류자가 사용자의 요구를 충족 하지 않는 경우 고유한 분류자를 만들어 교육할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbf32-198">When the built-in classifiers don't meet your needs, you can create and train your own classifiers.</span></span> <span data-ttu-id="dbf32-199">자체를 만드는 작업과 관련 된 작업은 훨씬 더 많이 수행 되지만 조직 요구 사항에 맞게 조정 하는 것이 훨씬 더 낫습니다.</span><span class="sxs-lookup"><span data-stu-id="dbf32-199">There's significantly more work involved with creating your own, but they'll be much better tailored to your organizations needs.</span></span> <span data-ttu-id="dbf32-200">미리 정의 된 분류자를 사용 하는 방법에 대 한 자세한 내용은 [기본 제공 분류자 사용](classifier-using-a-ready-to-use-classifier.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="dbf32-200">For more detail on how to use a pre-trained classifier, see [Using a built-in classifier](classifier-using-a-ready-to-use-classifier.md)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dbf32-201">Trainable 분류자를 만드는 사용자만이 해당 분류자가 수행한 예측을 학습 하 고 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbf32-201">Only the user who creates a trainable classifier can train and review predictions made by that classifier.</span></span>

#### <a name="process-flow-for-creating-trainable-classifiers"></a><span data-ttu-id="dbf32-202">Trainable 분류자를 만들기 위한 프로세스 흐름</span><span class="sxs-lookup"><span data-stu-id="dbf32-202">Process flow for creating trainable classifiers</span></span>

<span data-ttu-id="dbf32-203">승인 솔루션에서 사용 하기 위한 trainable 분류자 만들기 및 게시 (예: 보존 정책 및 통신 감독)는 다음 흐름을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="dbf32-203">Creating and publishing a trainable classifier for use in compliance solutions, such as retention policies and communication supervision, follows this flow.</span></span> <span data-ttu-id="dbf32-204">Trainable 분류자를 만드는 방법에 대 한 자세한 내용은 [trainable 분류자 만들기](classifier-creating-a-trainable-classifier.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="dbf32-204">For more detail on creating a trainable classifier see, [Creating a trainable classifier](classifier-creating-a-trainable-classifier.md).</span></span>

![프로세스 흐름 trainable 분류자](../media/classifier-trainable-classifier-flow.png)

## <a name="see-also"></a><span data-ttu-id="dbf32-206">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dbf32-206">See also</span></span>


- [<span data-ttu-id="dbf32-207">보존 레이블</span><span class="sxs-lookup"><span data-stu-id="dbf32-207">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="dbf32-208">보존 정책</span><span class="sxs-lookup"><span data-stu-id="dbf32-208">Retention policies</span></span>](retention-policies.md)
- [<span data-ttu-id="dbf32-209">DLP(데이터 손실 방지)</span><span class="sxs-lookup"><span data-stu-id="dbf32-209">Data loss prevention (DLP)</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="dbf32-210">민감도 레이블</span><span class="sxs-lookup"><span data-stu-id="dbf32-210">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="dbf32-211">중요한 정보 유형 엔터티 정의</span><span class="sxs-lookup"><span data-stu-id="dbf32-211">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="dbf32-212">문서 손가락 인쇄</span><span class="sxs-lookup"><span data-stu-id="dbf32-212">Document finger printing</span></span>](document-fingerprinting.md)
- [<span data-ttu-id="dbf32-213">정확한 데이터 일치</span><span class="sxs-lookup"><span data-stu-id="dbf32-213">Exact data match</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
