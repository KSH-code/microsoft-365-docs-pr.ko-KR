---
title: 정확한 데이터 일치 스키마 및 중요한 정보 유형 마법사 사용
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.date: ''
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 정확한 데이터 일치 스키마 및 중요한 정보 유형 마법사를 사용하는 방법에 대해 알아봅니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5fdf289c403d8c09342a1eac1434c4219bb7b13c
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861662"
---
# <a name="use-the-exact-data-match-schema-and-sensitive-information-type-wizard"></a><span data-ttu-id="97c01-103">정확한 데이터 일치 스키마 및 중요한 정보 유형 마법사 사용</span><span class="sxs-lookup"><span data-stu-id="97c01-103">Use the Exact Data Match Schema and Sensitive Information Type Wizard</span></span>

<span data-ttu-id="97c01-104">[EDM(정확한 데이터 일치) 기반 분류](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)를 사용하여 사용자 지정 중요한 정보 유형을 생성하려면 여러 단계를 거쳐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97c01-104">[Creating a custom sensitive information type with Exact Data Match (EDM) based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)  involves many steps.</span></span>  <span data-ttu-id="97c01-105">이 마법사를 사용하여 프로세스를 간소화하는 데 도움이 되는 Schema 및 SIT(중요한 정보 유형) 패턴(규칙 패키지) 파일을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97c01-105">You can use this wizard to create your schema and sensitive information type (SIT) pattern (rule package) files to help simplify the process.</span></span>

> [!NOTE]
> <span data-ttu-id="97c01-106">정확한 데이터 일치 스키마 및 중요 정보 유형 마법사는 월드 와이드 및 GCC 클라우드에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97c01-106">The Exact Data Match Schema and Sensitive Information Type Wizard is only available for the World Wide and GCC clouds only.</span></span>

<span data-ttu-id="97c01-107">이 마법사는 다음 대신 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97c01-107">This wizard can be used instead of the:</span></span>

- [<span data-ttu-id="97c01-108">중요한 정보 데이터베이스의 스키마 정의</span><span class="sxs-lookup"><span data-stu-id="97c01-108">Define the schema for your database of sensitive information</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#define-the-schema-for-your-database-of-sensitive-information)
- [<span data-ttu-id="97c01-109">패턴 설정(규칙 패키지)</span><span class="sxs-lookup"><span data-stu-id="97c01-109">Set up a pattern (rule package)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#set-up-a-rule-package)

<span data-ttu-id="97c01-110">[1단계: EDM 기반 분류 설정](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-1-set-up-edm-based-classification).</span><span class="sxs-lookup"><span data-stu-id="97c01-110">steps in [Part 1: Set up EDM-based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-1-set-up-edm-based-classification).</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="97c01-111">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="97c01-111">Pre-requisites</span></span>

1. <span data-ttu-id="97c01-112">EDM [ 워크플로 한 눈에 보기](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#the-work-flow-at-a-glance)를 통해 사용자 지정 중요한 정보 유형을 생성하는 단계를 숙지하세요.</span><span class="sxs-lookup"><span data-stu-id="97c01-112">Familiarize yourself with the steps to create a custom sensitive information type with EDM [work flow at a glance](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#the-work-flow-at-a-glance).</span></span>

2. <span data-ttu-id="97c01-113">[.csv 형식으로 중요한 데이터 저장](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#save-sensitive-data-in-csv-format) 섹션의 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="97c01-113">Perform the steps in the [Save sensitive data in .csv format](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#save-sensitive-data-in-csv-format) section.</span></span>

## <a name="use-the-exact-data-match-schema-and-sensitive-information-type-pattern-wizard"></a><span data-ttu-id="97c01-114">정확한 데이터 일치 스키마 및 중요한 정보 유형 패턴 마법사 사용</span><span class="sxs-lookup"><span data-stu-id="97c01-114">Use the exact data match schema and sensitive information type pattern wizard</span></span>

1. <span data-ttu-id="97c01-115">테넌트에 대한 Microsoft 365 규정 준수 센터에서 **데이터 분류** > **일치 데이터 추출** 로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="97c01-115">In the Microsoft 365 Compliance center for your tenant go to **Data classification** > **Exact data matches**.</span></span>

2. <span data-ttu-id="97c01-116">**EDM 스키마 생성** 을 선택하여 스키마 마법사 구성 플라이아웃을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="97c01-116">Choose **Create EDM schema** to open the schema wizard configuration flyout.</span></span>

![EDM 스키마 만들기 마법사 구성 플라이 아웃](../media/edm-schema-wizard-1.png)

3. <span data-ttu-id="97c01-118">적절한 **이름** 과 **설명** 을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="97c01-118">Fill in an appropriate **Name** and **Description**.</span></span>

4. <span data-ttu-id="97c01-119">해당 동작을 사용하려는 경우 모든 **Schema** 필드에 대해 문장 부호 및 문장 부호 무시를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="97c01-119">Choose **Ignore delimiters and punctuation for all schema fields** if you want that behavior.</span></span> <span data-ttu-id="97c01-120">대소문자나 구분 구분을 무시하기 위해 EDM을 구성하는 방법을 알아보는 자세한 내용은 [EDM(Exact Data Match)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)기반 분류를 사용하여 사용자 지정 중요한 정보 유형 만들기를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="97c01-120">To learn more about configuring EDM to ignore case or delimiters, see [Creating a custom sensitive information type with Exact Data Match (EDM) based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

5. <span data-ttu-id="97c01-121">**Schema 필드 #1** 에 대해 원하는 값을 입력하고 필요에 따라 필드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="97c01-121">Fill in your desired values for your **Schema field #1** and add more fields as needed.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="97c01-122">하나 이상의 스키마 필드를 검색 가능으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97c01-122">At least one, but no more than five of your schema fields must be designated as searchable.</span></span>

6. <span data-ttu-id="97c01-123">저장을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="97c01-123">Choose save.</span></span> <span data-ttu-id="97c01-124">스키마가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="97c01-124">Your schema will now be listed.</span></span>

7. <span data-ttu-id="97c01-125">**EDM 중요한 정보 유형** 과 **EDM 중요한 정보 유형** 을 선택하고 중요한 정보 유형 구성 마법사를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="97c01-125">Choose **EDM sensitive info types** and **Create EDM sensitive info type** to open the sensitive info type configuration wizard.</span></span>

8. <span data-ttu-id="97c01-126">**기존 EDM 스키마** 를 선택하고 목록에서 2-6단계에서 생성한 스키마를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="97c01-126">Choose **Choose an existing EDM schema** and choose the schema you created in steps 2-6 from the list.</span></span>

9. <span data-ttu-id="97c01-127">**다음** 을 선택하고 **패턴 생성** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="97c01-127">Choose **Next** and choose **Create pattern**.</span></span>

10. <span data-ttu-id="97c01-128">**신뢰 수준** 및 **기본 요소** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="97c01-128">Choose the **Confidence level** and **Primary element**.</span></span>  <span data-ttu-id="97c01-129">패턴을 구성하는 방법에 대한 자세한 내용은 [규정 준수 센터에서 사용자 지정 중요한 정보 유형 생성](create-a-custom-sensitive-information-type.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="97c01-129">To learn more about configuring a pattern, see [Create a custom sensitive information type in the Compliance Center](create-a-custom-sensitive-information-type.md)</span></span>

11.  <span data-ttu-id="97c01-130">연결할 **기본 요소에 대한 중요한 정보 유형** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="97c01-130">Choose the **Primary element's sensitive info type** to associate it with.</span></span> <span data-ttu-id="97c01-131">사용 가능한 중요한 정보 유형에 대한 자세한 내용은 [중요한 정보 유형 엔티티 정의](sensitive-information-type-entity-definitions.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="97c01-131">See [Sensitive Information Type Entity Definitions](sensitive-information-type-entity-definitions.md) to learn more about the available sensitive information types.</span></span>

12. <span data-ttu-id="97c01-132">**완료** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="97c01-132">Choose **Done**.</span></span>

13. <span data-ttu-id="97c01-133">원하는 **신뢰 수준 및 문자 근접성** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="97c01-133">Choose your desired **Confidence level and character proximity**.</span></span>  <span data-ttu-id="97c01-134">이 값은 전체 EDM 중요한 정보 유형에 대한 기본값이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="97c01-134">This will be the default value for the whole EDM sensitive info type</span></span>

13. <span data-ttu-id="97c01-135">EDM 중요한 **정보** 유형에 대한 추가 패턴을 만들 경우 패턴 만들기를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="97c01-135">Choose **Create pattern** if you want to create additional patterns for your EDM sensitive info type.</span></span>

14. <span data-ttu-id="97c01-136">**다음** 을 선택하고 **이름** 과 **관리자 설명** 을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="97c01-136">Choose **Next** and fill in a **Name** and **Description for admins**.</span></span>

15. <span data-ttu-id="97c01-137">검토하고 **제출** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="97c01-137">Review and choose **Submit**.</span></span>

<span data-ttu-id="97c01-138">중요한 정보 유형 패턴을 선택하여 편집 및 삭제 컨트롤의 표면을 선택하여 삭제하거나 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97c01-138">You can delete or edit the sensitive information type pattern by selecting it which surfaces the edit and delete controls.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="97c01-139">스키마를 제거하려면 해당 스키마가 EDM에 중요한 정보 유형과 이미 연결되어 있는 경우 먼저 EDM에 중요한 정보 유형을 삭제한 후 스키마를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97c01-139">If you want to remove a schema, and it is already associated with an EDM sensitive info type, you must first delete the EDM sensitive info type, then you can delete the schema.</span></span>

## <a name="post-creation-steps"></a><span data-ttu-id="97c01-140">만들기 후 단계</span><span class="sxs-lookup"><span data-stu-id="97c01-140">Post creation steps</span></span>

<span data-ttu-id="97c01-141">이 마법사를 사용하여 EDM 스키마 및 패턴(규칙 패키지) 파일을 생성한 후에도 [2 단계: 중요 데이터 해시 및 업로드](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-2-hash-and-upload-the-sensitive-data)를 완료해야 EDM 사용자 지정 정보 유형을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97c01-141">After you have used this wizard to create your EDM schema and pattern (rule package) files, you still have to perform the steps in [Part 2: Hash and upload the sensitive data](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-2-hash-and-upload-the-sensitive-data) before you can use the EDM custom sensitive information type.</span></span>

<span data-ttu-id="97c01-142">중요한 정보 테이블이 올바르게 업로드되었는지 확인한 후 제대로 작동하고 있는지 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97c01-142">After verifying that your sensitive information table has correctly been uploaded, you can test that it's working properly.</span></span>

1. <span data-ttu-id="97c01-143">개방형 **준수 센터**  >  **데이터 분류 중요한** 정보  >  **유형입니다.**</span><span class="sxs-lookup"><span data-stu-id="97c01-143">Open **Compliance center** > **Data classification** > **Sensitive Information Types**.</span></span>
2. <span data-ttu-id="97c01-144">목록에서 EDM SIT를 선택한  다음 플라이아웃 창에서 테스트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="97c01-144">Select your EDM SIT from the list and then select **Test** in the flyout pane.</span></span> 
3. <span data-ttu-id="97c01-145">업로드 중요한 정보 테이블의 일부 데이터가 포함된 항목을 만드는 경우를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97c01-145">Upload an item that contains data you want to detect, for example create an item that contains some of the data in your sensitive information table.</span></span> <span data-ttu-id="97c01-146">Schema에서 구성 가능한 일치 기능을 사용하여 무시된 개별 항목을 정의한 경우 항목에 해당 개별 항목과 함께 및 포함하지 않는 예제를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97c01-146">If you used the configurable match feature in your schema to define ignored delimiters, make sure the item includes examples with and without those delimiters.</span></span>
4. <span data-ttu-id="97c01-147">파일을 업로드하고 검사한 후 EDM SIT와 일치하는지 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="97c01-147">After the file has been uploaded and scanned, check for matches to your EDM SIT.</span></span>
5. <span data-ttu-id="97c01-148">SIT의 **Test** 함수에서 일치가 검색되면 해당 일치가 잘리거나 올바르게 추출되지 않는지 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="97c01-148">If the **Test** function in the SIT detects a match, check that it is not trimming it or extracting it incorrectly.</span></span> <span data-ttu-id="97c01-149">예를 들어 전체 문자열의 하위 문자열만 추출하여 검색하거나 다중 단어 문자열의 첫 번째 단어만 선택하거나 추출에 추가 기호나 문자를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97c01-149">For example by extracting only a substring of the full string it is supposed to detect, or picking up only the first word in a multi-word string, or including extra symbols or characters in the extraction.</span></span> <span data-ttu-id="97c01-150">정규식 [언어 참조에](/dotnet/standard/base-types/regular-expression-language-quick-reference) 대한 자세한 내용은 정규식 언어 - 빠른 참조를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="97c01-150">See [Regular Expression Language - Quick Reference](/dotnet/standard/base-types/regular-expression-language-quick-reference) for the regular expression language reference.</span></span> 

### <a name="troubleshooting"></a><span data-ttu-id="97c01-151">문제 해결</span><span class="sxs-lookup"><span data-stu-id="97c01-151">Troubleshooting</span></span>

<span data-ttu-id="97c01-152">일치하는 일치가 없는 경우 다음을 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="97c01-152">If you don't find any matches, try the following:</span></span>
- <span data-ttu-id="97c01-153">EDM 도구를 사용하여 중요한 데이터를 업로드하기 위한 지침에 설명된 명령을 사용하여 중요한 데이터가 올바르게 [업로드된지 확인합니다.](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)</span><span class="sxs-lookup"><span data-stu-id="97c01-153">Confirm that your sensitive data was uploaded correctly using the commands explained in [the guidance for uploading your sensitive data using the EDM tool](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>
- <span data-ttu-id="97c01-154">항목에 입력한 예제가 중요한 정보 표에 있으며 무시된 구분선이 올바른지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="97c01-154">Check that the examples you entered in the item are present in your sensitive information table and that the ignored delimiters are correct.</span></span>
- <span data-ttu-id="97c01-155">**각** 패턴에서 기본 요소를 구성할 때 사용한 SIT를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="97c01-155">**Test** the SIT you used when you configured the primary element in each of your patterns.</span></span> <span data-ttu-id="97c01-156">그러면 SIT가 항목의 예제와 일치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97c01-156">This will confirm that the SIT is able to match the examples in the item.</span></span> 
  -  <span data-ttu-id="97c01-157">EDM 형식의 기본 요소에 대해 선택한 SIT가 항목에서 일치 항목을 찾지 못하거나 예상보다 적은 일치 항목을 찾으면 콘텐츠에 있는 구분 및 구분기를 지원하는지 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="97c01-157">If the SIT you selected for a primary element in the EDM type doesn't find a match in the item or finds fewer matches than you expected, check that it supports separators and delimiters that exist in the content.</span></span> <span data-ttu-id="97c01-158">해당 schema에 정의된 무시된 디지타이터를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97c01-158">Be sure to include the ignored delimiters defined in your schema.</span></span> 
  -  <span data-ttu-id="97c01-159">Test **함수에서** 콘텐츠를 검색하지 못하면 선택한 SIT에 추가 키워드 또는 기타 유효성 검사에 대한 요구 사항이 포함되어 있지 않은지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="97c01-159">If the **Test** function does not detect any content at all, check if the SIT you selected includes requirements for additional keywords or other validations.</span></span> <span data-ttu-id="97c01-160">기본 제공 SITS에 대한 [](sensitive-information-type-entity-definitions.md) 자세한 내용은 중요한 정보 유형 엔터티 정의를 참조하여 각 유형과 일치하기 위한 최소 요구 사항을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="97c01-160">For the built-in SITs, see [Sensitive information types entity definitions](sensitive-information-type-entity-definitions.md) to verify what the minimum requirements are for matching each type.</span></span>
