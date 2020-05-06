---
title: 오류에 대한 콘텐츠 검색 쿼리 확인
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 11/30/2016
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 88898874-e262-4c5c-b6d2-4e697497fc74
ms.custom:
- seo-marvel-apr2020
description: 키워드 쿼리를 통해 콘텐츠 검색에 지원 되지 않는 문자 및 소문자 부울 연산자와 같은 오류 및 오타가 있는지 확인 하는 방법을 알아봅니다.
ms.openlocfilehash: 489afd8b2fe19742b63232d323197afecc257ccc
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035630"
---
# <a name="check-your-content-search-query-for-errors"></a><span data-ttu-id="0e064-103">오류에 대한 콘텐츠 검색 쿼리 확인</span><span class="sxs-lookup"><span data-stu-id="0e064-103">Check your Content Search query for errors</span></span>

<span data-ttu-id="0e064-104">콘텐츠 검색을 만들거나 편집할 때 Microsoft 365에서 지원 되지 않는 문자와 소문자 부울 연산자에 대 한 쿼리를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e064-104">When you create or edit a Content Search, you can have Microsoft 365 check your query for unsupported characters and lowercase Boolean operators.</span></span> <span data-ttu-id="0e064-105">미치는?</span><span class="sxs-lookup"><span data-stu-id="0e064-105">How?</span></span> <span data-ttu-id="0e064-106">콘텐츠 검색의 쿼리 페이지에서 **오타가 있는지 확인을** 클릭 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e064-106">Just click **Check query for typos** on the query page of a Content Search.</span></span> 
  
!["오타에 대 한 쿼리 확인"을 클릭 하 여 검색 쿼리를 검사 하 여 지원 되지 않는 문자](../media/e5314306-cfb2-481d-9b5c-13ce658156e7.png)
  
<span data-ttu-id="0e064-108">여기에는 검사 하는 지원 되지 않는 문자 목록이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e064-108">Here's a list of the unsupported characters that we check for.</span></span> <span data-ttu-id="0e064-109">지원 되지 않는 문자는 대개 숨겨지고 대개 검색 오류가 발생 하거나 의도 하지 않은 결과가 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e064-109">Unsupported characters are often hidden, and they typically cause a search error or return unintended results.</span></span>
  
- <span data-ttu-id="0e064-110">**스마트 따옴표** -둥근 작은따옴표나 큰따옴표 (굽은 따옴표 라고도 함)는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0e064-110">**Smart quotation marks** - Smart single and double quotation marks (also called curly quotes) aren't supported.</span></span> <span data-ttu-id="0e064-111">검색 쿼리에는 곧은 따옴표만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e064-111">Only straight quotation marks can be used in a search query.</span></span> 
    
- <span data-ttu-id="0e064-112">인쇄할 수 없는 문자와 **제어 되지 않는 문자** -인쇄할 수 없는 문자 및 제어 되는 문자는 부호 있는 기호를 나타내지 않습니다 (예: 영문자).</span><span class="sxs-lookup"><span data-stu-id="0e064-112">**Non-printable and control characters** - Non-printable and control characters don't represent a written symbol, such as an alpha-numeric character.</span></span> <span data-ttu-id="0e064-113">인쇄할 수 없는 문자 및 제어 문자의 예로는 텍스트 또는 별도의 텍스트 줄을 지정 하는 문자를 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e064-113">Examples of non-printable and control characters include characters that format text or separate lines of text.</span></span> 
    
- <span data-ttu-id="0e064-114">**왼쪽에서 오른쪽 및 오른쪽에서 왼쪽으로 표시** -이러한 표시는 왼쪽에서 오른쪽으로 쓰기 언어의 텍스트 방향 (예: 영어 및 스페인어) 및 오른쪽에서 왼쪽으로 쓰기 언어 (아랍어, 히브리어)를 나타내는 데 사용 되는 제어 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="0e064-114">**Left-to-right and right-to-left marks** - These marks are control characters used to indicate text direction for left-to-right languages (such as English and Spanish) and right-to-left languages (such as Arabic and Hebrew).</span></span>
    
- <span data-ttu-id="0e064-115">**소문자 부울 연산자** -검색 쿼리에 **NOT** **And**, **OR**등의 부울 연산자를 사용 하는 경우에는 대문자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e064-115">**Lowercase Boolean operators** - If you use a Boolean operator, such as **AND**, **OR**, and **NOT** in a search query, it must be uppercase.</span></span> <span data-ttu-id="0e064-116">쿼리에 오타가 있는지 여부를 확인 하는 경우 쿼리 구문에는 소문자 연산자를 사용할 수 있지만 부울 연산자가 사용 되는 것으로 표시 되는 경우가 많습니다. 예를 `(WordA or WordB) and (WordC or WordD)`들면입니다.</span><span class="sxs-lookup"><span data-stu-id="0e064-116">When we check a query for typos, the query syntax will often indicate that a Boolean operator is being used even though lowercase operators might be used; for example,  `(WordA or WordB) and (WordC or WordD)`.</span></span>
    
## <a name="what-happens-if-a-query-has-an-unsupported-character"></a><span data-ttu-id="0e064-117">쿼리에 지원 되지 않는 문자가 있으면 어떻게 되나요?</span><span class="sxs-lookup"><span data-stu-id="0e064-117">What happens if a query has an unsupported character?</span></span>

<span data-ttu-id="0e064-118">쿼리에서 지원 되지 않는 문자를 찾을 수 없는 경우 지원 되지 않는 문자가 발견 되었으며 대체 방법을 추천 하는 경고 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e064-118">If unsupported characters are found in your query, a warning message is displayed that says unsupported characters were found and suggests an alternative.</span></span> <span data-ttu-id="0e064-119">그런 다음 원래 쿼리를 유지 하거나 제안 된 수정 쿼리로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e064-119">You then have the option keep the original query or replace it with the suggested revised query.</span></span> <span data-ttu-id="0e064-120">다음은 이전 스크린샷에 검색 쿼리에 대 한 **오타가 있는지 확인** 을 클릭 하면 표시 되는 경고 메시지의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="0e064-120">Here's an example of the warning message that's displayed after you click **Check query for typos** for the search query in the previous screenshot.</span></span> <span data-ttu-id="0e064-121">원래 쿼리에는 스마트 시황 및 소문자 부울 연산자가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e064-121">Notice that the original query contains smart quotes and lowercase Boolean operators.</span></span> 
  
![쿼리에 대 한 제안 된 수정 내용으로 경고 메시지가 표시 됨](../media/23214b30-8e52-412c-bd80-63fb1b3ed52d.png)
  
## <a name="how-to-prevent-unsupported-characters-in-your-search-queries"></a><span data-ttu-id="0e064-123">검색 쿼리에서 지원 되지 않는 문자를 차단 하는 방법</span><span class="sxs-lookup"><span data-stu-id="0e064-123">How to prevent unsupported characters in your search queries</span></span>

<span data-ttu-id="0e064-124">지원 되지 않는 문자는 대개 쿼리 또는 쿼리 일부를 Microsoft Word 또는 Microsoft Excel 등의 다른 응용 프로그램에서 복사 하 여 콘텐츠 검색의 쿼리 페이지에 있는 키워드 상자에 붙여 넣으면 쿼리에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e064-124">Unsupported characters are typically added to a query when you copy the query or parts of the query from other applications (such as Microsoft Word or Microsoft Excel) and paste them in the keyword box on the query page of a Content Search.</span></span> <span data-ttu-id="0e064-125">지원 되지 않는 문자를 차단 하는 가장 좋은 방법은 키워드 상자에 쿼리를 입력 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0e064-125">The best way to prevent unsupported characters is to just type the query in the keyword box.</span></span> <span data-ttu-id="0e064-126">또는 Word 또는 Excel에서 쿼리를 복사한 다음 Microsoft 메모장과 같은 일반 텍스트 편집기에 붙여 넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e064-126">Or you can copy a query from Word or Excel, and then paste it in a plain text editor, such as Microsoft Notepad.</span></span> <span data-ttu-id="0e064-127">텍스트 파일을 저장 하 고 **인코딩** 드롭다운 목록에서 **ANSI** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e064-127">Save the text file and select **ANSI** in the **Encoding** drop-down list.</span></span> <span data-ttu-id="0e064-128">이렇게 하면 지원 되지 않는 문자나 서식이 모두 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e064-128">This will remove any formatting and unsupported characters.</span></span> <span data-ttu-id="0e064-129">그런 다음 텍스트 파일의 쿼리를 키워드 쿼리 상자에 복사 하 여 붙여 넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e064-129">Then you can copy and paste the query from the text file to the keyword query box.</span></span> 
