---
title: 정확한 데이터 일치 스키마 및 중요한 정보 유형 마법사 사용
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 정확한 데이터 일치 스키마 및 중요한 정보 유형 마법사를 사용하는 방법에 대해 알아봅니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2081de887e09794350222dac3527bb3ff932837a
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/16/2020
ms.locfileid: "49699159"
---
# <a name="use-the-exact-data-match-schema-and-sensitive-information-type-wizard"></a><span data-ttu-id="08177-103">정확한 데이터 일치 스키마 및 중요한 정보 유형 마법사 사용</span><span class="sxs-lookup"><span data-stu-id="08177-103">Use the Exact Data Match Schema and Sensitive Information Type Wizard</span></span>

<span data-ttu-id="08177-104">[EDM(정확한 데이터 일치) 기반 분류](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)를 사용하여 사용자 지정 중요한 정보 유형을 생성하려면 여러 단계를 거쳐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08177-104">[Creating a custom sensitive information type with Exact Data Match (EDM) based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)  involves many steps.</span></span>  <span data-ttu-id="08177-105">이 마법사를 사용하여 스키마와 중요한 정보 유형 패턴(규칙 패키지) 파일을 만들어 프로세스를 간소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08177-105">You can use this wizard to create your schema and sensitive information type pattern (rule package) files to help simplify the process.</span></span>

> [!NOTE]
> <span data-ttu-id="08177-106">정확한 데이터 일치 스키마 및 중요 정보 유형 마법사는 월드 와이드 및 GCC 클라우드에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08177-106">The Exact Data Match Schema and Sensitive Information Type Wizard is only available for the World Wide and GCC clouds only.</span></span>

<span data-ttu-id="08177-107">이 마법사는 다음 대신 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08177-107">This wizard can be used instead of the:</span></span>

- [<span data-ttu-id="08177-108">중요한 정보 데이터베이스의 스키마 정의</span><span class="sxs-lookup"><span data-stu-id="08177-108">Define the schema for your database of sensitive information</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#define-the-schema-for-your-database-of-sensitive-information)
- [<span data-ttu-id="08177-109">패턴 설정(규칙 패키지)</span><span class="sxs-lookup"><span data-stu-id="08177-109">Set up a pattern (rule package)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#set-up-a-rule-package)

<span data-ttu-id="08177-110">[1단계: EDM 기반 분류 설정](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-1-set-up-edm-based-classification).</span><span class="sxs-lookup"><span data-stu-id="08177-110">steps in [Part 1: Set up EDM-based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-1-set-up-edm-based-classification).</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="08177-111">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="08177-111">Pre-requisites</span></span>

1. <span data-ttu-id="08177-112">EDM [ 워크플로 한 눈에 보기](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#the-work-flow-at-a-glance)를 통해 사용자 지정 중요한 정보 유형을 생성하는 단계를 숙지하세요.</span><span class="sxs-lookup"><span data-stu-id="08177-112">Familiarize yourself with the steps to create a custom sensitive information type with EDM [work flow at a glance](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#the-work-flow-at-a-glance).</span></span>

2. <span data-ttu-id="08177-113">[.csv 형식으로 중요한 데이터 저장](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#save-sensitive-data-in-csv-format) 섹션의 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="08177-113">Perform the steps in the [Save sensitive data in .csv format](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#save-sensitive-data-in-csv-format) section.</span></span>

## <a name="use-the-exact-data-match-schema-and-sensitive-information-type-pattern-wizard"></a><span data-ttu-id="08177-114">정확한 데이터 일치 스키마 및 중요한 정보 유형 패턴 마법사 사용</span><span class="sxs-lookup"><span data-stu-id="08177-114">Use the exact data match schema and sensitive information type pattern wizard</span></span>

1. <span data-ttu-id="08177-115">테넌트에 대한 Microsoft 365 규정 준수 센터에서 **데이터 분류** > **일치 데이터 추출** 로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="08177-115">In the Microsoft 365 Compliance center for your tenant go to **Data classification** > **Exact data matches**.</span></span>

2. <span data-ttu-id="08177-116">**EDM 스키마 생성** 을 선택하여 스키마 마법사 구성 플라이아웃을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="08177-116">Choose **Create EDM schema** to open the schema wizard configuration flyout.</span></span>

![EDM 스키마 만들기 마법사 구성 플라이 아웃](../media/edm-schema-wizard-1.png)

3. <span data-ttu-id="08177-118">적절한 **이름** 과 **설명** 을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="08177-118">Fill in an appropriate **Name** and **Description**.</span></span>

4. <span data-ttu-id="08177-119">해당 동작을 수행하려면 **모든 스키마 필드에 대한 구분 기호 및 구두점 무시** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="08177-119">Choose **Ignore delimiters and punctuations for all schema fields** if you want that behavior.</span></span> <span data-ttu-id="08177-120">대/소문자나 구분 기호를 무시하도록 EDM을 구성하는 방법에 대한 자세한 내용은 [EDM(정확한 데이터 일치) 기반 분류를 사용하여 사용자 지정 중요한 정보 유형 생성](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="08177-120">To learn more about configuring EDM to ignore case or delimitere, see [Creating a custom sensitive information type with Exact Data Match (EDM) based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

5. <span data-ttu-id="08177-121">**Schema 필드 #1** 에 대해 원하는 값을 입력하고 필요에 따라 필드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="08177-121">Fill in your desired values for your **Schema field #1** and add more fields as needed.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="08177-122">하나 이상의 스키마 필드를 검색 가능으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08177-122">At least one, but no more than five of your schema fields must be designated as searchable.</span></span>

6. <span data-ttu-id="08177-123">저장을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="08177-123">Choose save.</span></span> <span data-ttu-id="08177-124">스키마가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="08177-124">Your schema will now be listed.</span></span>

7. <span data-ttu-id="08177-125">**EDM 중요한 정보 유형** 과 **EDM 중요한 정보 유형** 을 선택하고 중요한 정보 유형 구성 마법사를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="08177-125">Choose **EDM sensitive info types** and **Create EDM sensitive info type** to open the sensitive info type configuration wizard.</span></span>

8. <span data-ttu-id="08177-126">**기존 EDM 스키마** 를 선택하고 목록에서 2-6단계에서 생성한 스키마를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="08177-126">Choose **Choose an existing EDM schema** and choose the schema you created in steps 2-6 from the list.</span></span>

9. <span data-ttu-id="08177-127">**다음** 을 선택하고 **패턴 생성** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="08177-127">Choose **Next** and choose **Create pattern**.</span></span>

10. <span data-ttu-id="08177-128">**신뢰 수준** 및 **기본 요소** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="08177-128">Choose the **Confidence level** and **Primary element**.</span></span>  <span data-ttu-id="08177-129">패턴을 구성하는 방법에 대한 자세한 내용은 [규정 준수 센터에서 사용자 지정 중요한 정보 유형 생성](create-a-custom-sensitive-information-type.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="08177-129">To learn more about configuring a pattern, see [Create a custom sensitive information type in the Compliance Center](create-a-custom-sensitive-information-type.md)</span></span>

11.  <span data-ttu-id="08177-130">연결할 **기본 요소에 대한 중요한 정보 유형** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="08177-130">Choose the **Primary element's sensitive info type** to associate it with.</span></span> <span data-ttu-id="08177-131">사용 가능한 중요한 정보 유형에 대한 자세한 내용은 [중요한 정보 유형 엔티티 정의](sensitive-information-type-entity-definitions.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="08177-131">See [Sensitive Information Type Entity Definitions](sensitive-information-type-entity-definitions.md) to learn more about the available sensitive information types.</span></span>

12. <span data-ttu-id="08177-132">**완료** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="08177-132">Choose **Done**.</span></span>

13. <span data-ttu-id="08177-133">원하는 **신뢰 수준 및 문자 근접성** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="08177-133">Choose your desired **Confidence level and character proximity**.</span></span>  <span data-ttu-id="08177-134">이 값은 전체 EDM 중요한 정보 유형에 대한 기본값이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08177-134">This will be the default value for the whole EDM sensitive info type</span></span>

13. <span data-ttu-id="08177-135">EDM 중요한 정보 유형에 대한 추가 패턴을 만들려는 경우 **패턴 생성** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="08177-135">Choose **Create pattern** if you want to creaet additional patterns for your EDM sensitive info type.</span></span>

14. <span data-ttu-id="08177-136">**다음** 을 선택하고 **이름** 과 **관리자 설명** 을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="08177-136">Choose **Next** and fill in a **Name** and **Description for admins**.</span></span>

15. <span data-ttu-id="08177-137">검토하고 **제출** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="08177-137">Review and choose **Submit**.</span></span>

<span data-ttu-id="08177-138">중요한 정보 유형 패턴을 선택하여 편집 및 삭제 컨트롤의 표면을 선택하여 삭제하거나 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08177-138">You can delete or edit the sensitive information type pattern by selecting it which surfaces the edit and delete controls.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="08177-139">스키마를 제거하려면 해당 스키마가 EDM에 중요한 정보 유형과 이미 연결되어 있는 경우 먼저 EDM에 중요한 정보 유형을 삭제한 후 스키마를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08177-139">If you want to remove a schema, and it is already associated with an EDM sensitive info type, you must first delete the EDM sensitive info type, then you can delete the schema.</span></span>

## <a name="post-steps"></a><span data-ttu-id="08177-140">이후 단계</span><span class="sxs-lookup"><span data-stu-id="08177-140">Post steps</span></span>

<span data-ttu-id="08177-141">이 마법사를 사용하여 EDM 스키마 및 패턴(규칙 패키지) 파일을 생성한 후에도 [2 단계: 중요 데이터 해시 및 업로드](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-2-hash-and-upload-the-sensitive-data)를 완료해야 EDM 사용자 지정 정보 유형을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08177-141">After you have used this wizard to create your EDM schema and pattern (rule package) files, you still have to perform the steps in [Part 2: Hash and upload the sensitive data](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-2-hash-and-upload-the-sensitive-data) before you can use the EDM custom sensitive information type.</span></span>