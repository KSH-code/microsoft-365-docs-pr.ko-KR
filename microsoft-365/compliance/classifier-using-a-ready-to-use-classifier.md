---
title: 보존 레이블을 사용 하 여 기본 제공 분류자 테스트 (미리 보기)
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
description: Microsoft 365에는 조직 전체에서 콘텐츠를 식별 하 고 레이블을 지정 하는 데 사용할 수 있는 다양 한 기본 제공 분류자가 제공 됩니다. 이 항목에서는 이러한 분류자 사용을 준비 하는 방법을 보여 줍니다.
ms.openlocfilehash: fad35d72c4c40c7b79cba4cb286ccc0f5bb5ab8d
ms.sourcegitcommit: 22e9f54d0d3ead2be91a38d49325308c70f43f90
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2020
ms.locfileid: "44262549"
---
# <a name="testing-built-in-classifiers-using-retention-labels-preview"></a><span data-ttu-id="70192-104">보존 레이블을 사용 하 여 기본 제공 분류자 테스트 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="70192-104">Testing built-in classifiers using retention labels (preview)</span></span>

<span data-ttu-id="70192-105">Microsoft는 특정 콘텐츠 범주를 식별 하는 데 도움이 될 수 있는 다섯 가지 분류자를 교육 하 고 테스트 했습니다.</span><span class="sxs-lookup"><span data-stu-id="70192-105">Microsoft has trained and tested five classifiers which can help to identify certain categories of content.</span></span> <span data-ttu-id="70192-106">이러한 분류자는 `Ready to use` 기본적으로 그룹에 표시 되며 매우 큰 예제 데이터 집합을 사용 하 여 교육을 받은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="70192-106">These classifiers show up in the `Ready to use` group by default and were trained using very large sample data sets.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="70192-107">분류 및 레이블 지정 워크플로에 기본 제공 분류자를 사용 하기 전에 분류 예측이 예상과 맞는지 확인 하기 위해 범주에 적합 한 조직의 콘텐츠 샘플에서이를 테스트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70192-107">Before using built-in classifiers in your classification and labeling workflow, you should test it against a sample of your organization's content that you feel fits the category to verify that its classification predictions meet your expectations.</span></span>

<span data-ttu-id="70192-108">Trainable 분류자에 대 한 자세한 내용은 [trainable 분류자 (preview) 시작](classifier-getting-started-with.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="70192-108">For more information on trainable classifiers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span>

<span data-ttu-id="70192-109">Microsoft 365에는 다음과 같이 권장 되는 5 가지 기본 제공 분류자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70192-109">Microsoft 365 comes with five recommended built-in classifiers:</span></span>

> [!CAUTION]
> <span data-ttu-id="70192-110">많은 수의 가양성을 **생성 하 여 방식의 기본 제공** 분류자를 사용 중입니다.</span><span class="sxs-lookup"><span data-stu-id="70192-110">We are deprecating the **Offensive Language** built-in classifier because it has been producing a high number of false positives.</span></span> <span data-ttu-id="70192-111">이 도구를 사용 하지 않고 현재 사용 중인 경우 비즈니스 프로세스를 외부에서 이동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70192-111">Don't use it and if you are currently using it, you should move your business processes off of it.</span></span> <span data-ttu-id="70192-112">**위협**, **불경**및 **Harassment** 기본 제공 분류자를 대신 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="70192-112">We recommend using the **Threat**, **Profanity**, and **Harassment** built-in classifiers instead.</span></span>

- <span data-ttu-id="70192-113">**다시 시작**: 지원자 개인, 교육, 전문가 자격, 작업 환경 및 기타 개인 식별 정보에 해당 하는 텍스트 계정인 항목을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="70192-113">**Resumes**: detects items that are textual accounts of an applicant's personal, educational, professional qualifications, work experience, and other personally identifying information.</span></span>
- <span data-ttu-id="70192-114">**소스 코드**: GitHub에서 상위 25 사용 컴퓨터 프로그래밍 언어에 작성 된 지침 및 문 집합을 포함 하는 항목을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="70192-114">**Source Code**: detects items that contain a set of instructions and statements written in the top 25 used computer programming languages on GitHub.</span></span>

|<span data-ttu-id="70192-115">언어 이름</span><span class="sxs-lookup"><span data-stu-id="70192-115">language name</span></span>|||||
|---------|---------|---------|---------|---------|
|<span data-ttu-id="70192-116">ActionScript</span><span class="sxs-lookup"><span data-stu-id="70192-116">ActionScript</span></span>|<span data-ttu-id="70192-117">C</span><span class="sxs-lookup"><span data-stu-id="70192-117">C</span></span>        |<span data-ttu-id="70192-118">& #</span><span class="sxs-lookup"><span data-stu-id="70192-118">C#</span></span>       |<span data-ttu-id="70192-119">C + +</span><span class="sxs-lookup"><span data-stu-id="70192-119">C++</span></span>     |<span data-ttu-id="70192-120">Clojure</span><span class="sxs-lookup"><span data-stu-id="70192-120">Clojure</span></span>  |
|<span data-ttu-id="70192-121">CoffeeScript</span><span class="sxs-lookup"><span data-stu-id="70192-121">CoffeeScript</span></span>|<span data-ttu-id="70192-122">시트</span><span class="sxs-lookup"><span data-stu-id="70192-122">CSS</span></span>     |<span data-ttu-id="70192-123">갈</span><span class="sxs-lookup"><span data-stu-id="70192-123">Go</span></span>       |<span data-ttu-id="70192-124">Haskell</span><span class="sxs-lookup"><span data-stu-id="70192-124">Haskell</span></span> |<span data-ttu-id="70192-125">HTML</span><span class="sxs-lookup"><span data-stu-id="70192-125">HTML</span></span>     |
|<span data-ttu-id="70192-126">Java</span><span class="sxs-lookup"><span data-stu-id="70192-126">Java</span></span>     |<span data-ttu-id="70192-127">JavaScript</span><span class="sxs-lookup"><span data-stu-id="70192-127">JavaScript</span></span>|<span data-ttu-id="70192-128">Lua</span><span class="sxs-lookup"><span data-stu-id="70192-128">Lua</span></span>      |<span data-ttu-id="70192-129">MATLAB</span><span class="sxs-lookup"><span data-stu-id="70192-129">MATLAB</span></span>   |<span data-ttu-id="70192-130">목표-C</span><span class="sxs-lookup"><span data-stu-id="70192-130">Objective-C</span></span>|
|<span data-ttu-id="70192-131">Perl</span><span class="sxs-lookup"><span data-stu-id="70192-131">Perl</span></span>     |<span data-ttu-id="70192-132">PHP</span><span class="sxs-lookup"><span data-stu-id="70192-132">PHP</span></span>      |<span data-ttu-id="70192-133">Python</span><span class="sxs-lookup"><span data-stu-id="70192-133">Python</span></span>   |<span data-ttu-id="70192-134">이력서</span><span class="sxs-lookup"><span data-stu-id="70192-134">R</span></span>        |<span data-ttu-id="70192-135">Ruby</span><span class="sxs-lookup"><span data-stu-id="70192-135">Ruby</span></span>     |
|<span data-ttu-id="70192-136">Scala</span><span class="sxs-lookup"><span data-stu-id="70192-136">Scala</span></span>    |<span data-ttu-id="70192-137">셸</span><span class="sxs-lookup"><span data-stu-id="70192-137">Shell</span></span>    |<span data-ttu-id="70192-138">Swift</span><span class="sxs-lookup"><span data-stu-id="70192-138">Swift</span></span>    |<span data-ttu-id="70192-139">Tex</span><span class="sxs-lookup"><span data-stu-id="70192-139">Tex</span></span>      |<span data-ttu-id="70192-140">Vim 스크립트</span><span class="sxs-lookup"><span data-stu-id="70192-140">Vim Script</span></span>|

- <span data-ttu-id="70192-141">**Harassment**: 레이스, ethnicity, religion, 국립 근원, 성별, 성적 방향, 연령, 장애 등의 특성을 기반으로 하 여 한 명 이상의 개인이 대상으로 하는 공격적인 언어 텍스트 항목의 특정 범주를 감지 합니다.</span><span class="sxs-lookup"><span data-stu-id="70192-141">**Harassment**: detects a specific category of offensive language text items related to offensive conduct targeting one or multiple individuals based on the following traits: race, ethnicity, religion, national origin, gender, sexual orientation, age, disability.</span></span>
- <span data-ttu-id="70192-142">**불경**: 대부분의 사용자를 embarrass 하는 식이 포함 된 공격적인 언어 텍스트 항목의 특정 범주를 감지 합니다.</span><span class="sxs-lookup"><span data-stu-id="70192-142">**Profanity**: detects a specific category of offensive language text items that contain expressions that embarrass most people.</span></span>
- <span data-ttu-id="70192-143">**위협**: 사용자 또는 속성에 대 한 폭력을 커밋하거나 물리적인 손상을 주거나 위협에 관련 된 비속어 텍스트 항목의 특정 범주를 감지 합니다.</span><span class="sxs-lookup"><span data-stu-id="70192-143">**Threat**: detects a specific category of offensive language text items related to threats to commit violence or do physical harm or damage to a person or property,</span></span>

> [!IMPORTANT]
> <span data-ttu-id="70192-144">비속어, harassment, 비속어 및 threat 분류자는 검색 가능한 텍스트만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70192-144">Please note that the offensive language, harassment, profanity, and threat classifiers only work with searchable text are not exhaustive or complete.</span></span> <span data-ttu-id="70192-145">추가적으로, 언어 및 문화 표준이 지속적으로 변경 되 고 이러한 현실에 따라 Microsoft는 이러한 분류자를 업데이트할 수 있는 권리를 보유 합니다.</span><span class="sxs-lookup"><span data-stu-id="70192-145">Further, language and cultural standards continually change, and in light of these realities, Microsoft reserves the right to update these classifiers in its discretion.</span></span> <span data-ttu-id="70192-146">이 분류자는 사용 중인 공격적인 및 기타 언어를 모니터링 하는 데 도움이 될 수 있지만, 이러한 언어의 결과를 해결 하는 것이 아니므로 조직의 해당 언어 사용에 대 한 다양 한 모니터링 또는 대응 수단을 제공 하기 위한 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="70192-146">While the classifiers may assist your organization in monitoring offensive and other language used, the classifiers do not address consequences of such language and are not intended to provide your organization's sole means of monitoring or responding to the use of such language.</span></span> <span data-ttu-id="70192-147">Microsoft 또는 해당 자회사가 아닌 조직은 미리 훈련 된 분류자로 식별 되는 콘텐츠의 모니터링, 적용, 차단, 제거 및 보존과 관련 된 모든 결정을 계속 담당 합니다.</span><span class="sxs-lookup"><span data-stu-id="70192-147">Your organization, and not Microsoft or its subsidiaries, remains responsible for all decisions related to monitoring, enforcement, blocking, removal and retention of any content identified by a pre-trained classifier.</span></span>

## <a name="how-to-verify-that-a-built-in-classifier-will-meet-your-needs"></a><span data-ttu-id="70192-148">기본 제공 분류자가 사용자의 요구를 충족 하는지 확인 하는 방법</span><span class="sxs-lookup"><span data-stu-id="70192-148">How to verify that a built-in classifier will meet your needs</span></span>

1. <span data-ttu-id="70192-149">테스트 중인 범주에서 기본 제공 분류자의 범주 (긍정 일치) 및 포함 되지 않은 항목 (음수 일치)이 있는 삭제 가능한 테스트 콘텐츠를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="70192-149">Collect disposable test content items that you feel belong in the category of the built-in classifier (positive matches) and ones that shouldn't be included (negative matches) in the category you're testing.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="70192-150">샘플 항목은 암호화 하지 않아야 하며 영어로 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70192-150">The sample items must not be encrypted and they must be in English.</span></span>

2. <span data-ttu-id="70192-151">전용 SharePoint Online 폴더를 만듭니다. 폴더를 검색 인덱스에 추가할 때까지 적어도 1 시간 이상 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="70192-151">Create a dedicated SharePoint Online folder; wait at least an hour for the folder to be added to the search index.</span></span> <span data-ttu-id="70192-152">폴더 URL을 기록해 둡니다.</span><span class="sxs-lookup"><span data-stu-id="70192-152">Make note of the folder URL.</span></span>

3. <span data-ttu-id="70192-153">준수 관리자 또는 보안 관리자 역할 액세스를 사용 하 여 microsoft 365 준수 센터에 로그인 하 고 **microsoft 365 준수 센터**  >  **레코드 관리 (미리 보기)**  >  **레이블 정책** 탭을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="70192-153">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** > **Records management (preview)** > **Label policies** tab.</span></span>

4. <span data-ttu-id="70192-154">`Auto-apply a label`을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="70192-154">Choose `Auto-apply a label`.</span></span>

5. <span data-ttu-id="70192-155">`Choose a label to auto-apply`을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="70192-155">Choose `Choose a label to auto-apply`.</span></span>

6. <span data-ttu-id="70192-156">`Create new labels`이 테스트에만 사용할 레이블을 선택 하 고 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="70192-156">Choose `Create new labels` and create a label for use just with this test.</span></span> <span data-ttu-id="70192-157">이 경우 `Retention` 로를로 설정 `off` 합니다.</span><span class="sxs-lookup"><span data-stu-id="70192-157">When you do this, leave `Retention` set to `off`.</span></span> <span data-ttu-id="70192-158">보존 또는 기타 작업을 설정 하지 않으려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="70192-158">You don't want to turn on any retention or other actions.</span></span> <span data-ttu-id="70192-159">이 경우에는 작업을 적용 하지 않고 보존 레이블을 단순히 텍스트 레이블로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="70192-159">In this case, you'll be using the retention label simply as a text label, without enforcing any actions.</span></span> <span data-ttu-id="70192-160">예를 들어 작업 없이 "SourceCode 분류자 test" 라는 보존 레이블을 만든 다음 해당 보존 레이블을 조건으로 소스 코드 분류자가 있는 콘텐츠에 자동으로 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70192-160">For example, you can create a retention label named "SourceCode classifier test" with no actions, and then auto-apply that retention label to content that has Source code classifier as a condition.</span></span> <span data-ttu-id="70192-161">보존 레이블 만들기에 대 한 자세한 내용은 [Overview (보존 레이블](labels.md))를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="70192-161">To learn more about creating retention labels, see [Overview of retention labels](labels.md).</span></span>
  
7. <span data-ttu-id="70192-162">`Auto-apply a label`을 선택 하 고을 클릭 `Choose a label to auto-apply` 합니다.</span><span class="sxs-lookup"><span data-stu-id="70192-162">Choose `Auto-apply a label` and then `Choose a label to auto-apply`.</span></span> <span data-ttu-id="70192-163">조건 기반 자동 적용 레이블을 사용 하는 방법에 대 한 자세한 내용은 [조건에 따라 보존 레이블 정책 자동 적용](labels.md#applying-a-retention-label-automatically-based-on-conditions)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="70192-163">To learn more about using condition based auto-apply a label see, [auto-apply retention label policy based on a condition](labels.md#applying-a-retention-label-automatically-based-on-conditions).</span></span>

8. <span data-ttu-id="70192-164">목록에서 테스트 레이블을 선택 하 고를 선택 `Next` 합니다.</span><span class="sxs-lookup"><span data-stu-id="70192-164">Choose your test label from the list and choose `Next`.</span></span>

9. <span data-ttu-id="70192-165">`Apply label to content that matches a trainable classifier`을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="70192-165">Choose `Apply label to content that matches a trainable classifier`.</span></span>

![조건으로 분류자 선택](../media/classifier-pre-trained-apply-label-match-trainable-classifier.png)<span data-ttu-id="70192-167">.</span><span class="sxs-lookup"><span data-stu-id="70192-167">.</span></span>

10. <span data-ttu-id="70192-168">이 경우 목록에서 분류자를 선택 합니다.`Source Code`</span><span class="sxs-lookup"><span data-stu-id="70192-168">Choose your classifier from the list, in this case `Source Code`</span></span>

11. <span data-ttu-id="70192-169">정책 이름 (예: "소스 코드 기본 제공 분류자 test")을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="70192-169">Name the policy, for example "Source code built-in classifier test".</span></span>

12. <span data-ttu-id="70192-170">`Let me choose specific locations`을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="70192-170">Choose `Let me choose specific locations`.</span></span>

13. <span data-ttu-id="70192-171">를 제외한 모든 위치 `SharePoint sites` 를 해제 하 고를 선택 `Choose sites` 합니다.</span><span class="sxs-lookup"><span data-stu-id="70192-171">Turn off all locations except `SharePoint sites` and choose `Choose sites`.</span></span>

14. <span data-ttu-id="70192-172">2 단계에 해당 하는 사이트의 URL을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="70192-172">Enter the URL for the site from step 2.</span></span>

15. <span data-ttu-id="70192-173">마법사를 완료 하 고`Auto-apply`</span><span class="sxs-lookup"><span data-stu-id="70192-173">Finish the wizard and choose `Auto-apply`</span></span>

16. <span data-ttu-id="70192-174">테스트 항목을 전용 SharePoint Online 폴더에 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="70192-174">Place the test items into the dedicated SharePoint Online folder.</span></span>

17. <span data-ttu-id="70192-175">레이블이 적용 되는 시간을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="70192-175">Allow an hour for the label to be applied.</span></span>

18. <span data-ttu-id="70192-176">레이블에 대 한 문서의 속성을 확인 하 여 해당 분류자가 필요한 대로 테스트 콘텐츠를 포함 하 고 제외 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="70192-176">Check the properties of the documents for the label to see if the classifier included and excluded the test content as you expected.</span></span>

19. <span data-ttu-id="70192-177">레이블이 지정 된 항목을 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="70192-177">Review the items that were labeled.</span></span>

20. <span data-ttu-id="70192-178">테스트를 완료 한 경우 콘텐츠 및 레이블 정책을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="70192-178">Delete the content and the label policy if you're done with your testing.</span></span>

<span data-ttu-id="70192-179">참고 항목:</span><span class="sxs-lookup"><span data-stu-id="70192-179">See also:</span></span>

- [<span data-ttu-id="70192-180">학습 가능한 분류자 시작 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="70192-180">Getting started with trainable classifiers (preview)</span></span>](classifier-getting-started-with.md)
- [<span data-ttu-id="70192-181">보존 레이블 개요</span><span class="sxs-lookup"><span data-stu-id="70192-181">Overview of retention labels</span></span>](labels.md)
- [<span data-ttu-id="70192-182">조건에 따라 보존 레이블 정책 자동 적용</span><span class="sxs-lookup"><span data-stu-id="70192-182">Auto-apply retention label policy based on a condition</span></span>](labels.md#applying-a-retention-label-automatically-based-on-conditions)
