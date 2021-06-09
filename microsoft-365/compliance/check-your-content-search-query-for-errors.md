---
title: 검색 쿼리에서 오류 확인
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 88898874-e262-4c5c-b6d2-4e697497fc74
ms.custom: seo-marvel-apr2020
description: 검색을 실행하기 전에 eDiscovery 검색에 대한 키워드 쿼리에서 오류 및 오타를 검색하는 방법을 학습합니다.
ms.openlocfilehash: 9c041ca690df3306347cbca77df3ba9639801245
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311691"
---
# <a name="check-your-search-query-for-errors"></a><span data-ttu-id="34f43-103">검색 쿼리에서 오류 확인</span><span class="sxs-lookup"><span data-stu-id="34f43-103">Check your search query for errors</span></span>
  
<span data-ttu-id="34f43-104">다음은 콘텐츠 검색 및 Core eDiscovery에 대한 검색 쿼리에서 확인한 지원되지 않는 문자 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="34f43-104">Here's a list of the unsupported characters that we check for in search queries for Content search and Core eDiscovery.</span></span> <span data-ttu-id="34f43-105">일반적으로 검색 오류를 발생하거나 의도하지 않은 결과를 반환하는 데 사용할 수 없는 문자가 숨겨집니다.</span><span class="sxs-lookup"><span data-stu-id="34f43-105">Unsupported characters are often hidden, and they typically cause a search error or return unintended results.</span></span>
  
- <span data-ttu-id="34f43-106">**똑똑한 따옴표** - 똑똑한 단일 및 이중 따옴표(희미한 따옴표라고도 부호)는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="34f43-106">**Smart quotation marks** - Smart single and double quotation marks (also called curly quotes) aren't supported.</span></span> <span data-ttu-id="34f43-107">검색 쿼리에는 곧은 인용 부호만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34f43-107">Only straight quotation marks can be used in a search query.</span></span> 

- <span data-ttu-id="34f43-108">**인쇄할** 수 없는 문자와 컨트롤 문자 - 인쇄할 수 없는 문자와 컨트롤 문자는 영문자 같은 쓴 기호를 나타내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="34f43-108">**Non-printable and control characters** - Non-printable and control characters don't represent a written symbol, such as an alpha-numeric character.</span></span> <span data-ttu-id="34f43-109">인쇄할 수 없는 문자와 컨트롤 문자의 예로는 텍스트 서식을 지정하는 문자나 별도의 텍스트 줄이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34f43-109">Examples of non-printable and control characters include characters that format text or separate lines of text.</span></span> 

- <span data-ttu-id="34f43-110">**왼쪽에서 오른쪽** 및 오른쪽에서 왼쪽으로 표시 - 이러한 표시는 왼쪽에서 오른쪽으로 쓰는 언어(예: 영어 및 스페인어) 및 오른쪽에서 왼쪽으로 쓰는 언어(예: 아랍어 및 Hebrew)의 텍스트 방향을 나타내는 데 사용되는 컨트롤 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="34f43-110">**Left-to-right and right-to-left marks** - These marks are control characters used to indicate text direction for left-to-right languages (such as English and Spanish) and right-to-left languages (such as Arabic and Hebrew).</span></span>

- <span data-ttu-id="34f43-111">**소문자 부울** 연산자 - 검색 쿼리에서 **AND**, **OR** 및 **NOT과** 같은 부울 연산자를 사용하는 경우 대문자입니다.</span><span class="sxs-lookup"><span data-stu-id="34f43-111">**Lowercase Boolean operators** - If you use a Boolean operator, such as **AND**, **OR**, and **NOT** in a search query, it must be uppercase.</span></span> <span data-ttu-id="34f43-112">쿼리에서 오타를 확인할 때 쿼리 구문은 소문자 연산자를 사용할 수 있는 경우에도 부울 연산자를 사용 중입니다. 예를 들면  `(WordA or WordB) and (WordC or WordD)` 입니다.</span><span class="sxs-lookup"><span data-stu-id="34f43-112">When we check a query for typos, the query syntax will often indicate that a Boolean operator is being used even though lowercase operators might be used; for example,  `(WordA or WordB) and (WordC or WordD)`.</span></span>

## <a name="what-happens-if-a-query-has-an-unsupported-character"></a><span data-ttu-id="34f43-113">쿼리에 미지원 문자가 있는 경우 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="34f43-113">What happens if a query has an unsupported character?</span></span>

<span data-ttu-id="34f43-114">쿼리에서 미지원 문자가 발견되면 해당 문자가 발견되고 대안을 제안하는 경고 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="34f43-114">If unsupported characters are found in your query, a warning message is displayed that says unsupported characters were found and suggests an alternative.</span></span> <span data-ttu-id="34f43-115">그런 다음 원래 쿼리를 그대로 유지하거나 수정된 쿼리로 대체할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34f43-115">You then have the option keep the original query or replace it with the suggested revised query.</span></span>

<span data-ttu-id="34f43-116">다음은 이전 스크린샷에서 검색 쿼리에 대한 오타에 대한 쿼리 확인을 클릭한 후 표시되는 경고 메시지의 예입니다. </span><span class="sxs-lookup"><span data-stu-id="34f43-116">Here's an example of the warning message that's displayed after you click **Check query for typos** for the search query in the previous screenshot.</span></span> <span data-ttu-id="34f43-117">원래 쿼리에서 똑똑한 따옴표와 소문자 부울 연산자를 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="34f43-117">Note the original query used smart quotes and lowercase Boolean operators.</span></span>
  
![쿼리에 대한 제안된 변경과 함께 경고 메시지가 표시됩니다.](../media/23214b30-8e52-412c-bd80-63fb1b3ed52d.png)
  
## <a name="how-to-prevent-unsupported-characters-in-your-search-queries"></a><span data-ttu-id="34f43-119">검색 쿼리에서 지원되지 않는 문자를 방지하는 방법</span><span class="sxs-lookup"><span data-stu-id="34f43-119">How to prevent unsupported characters in your search queries</span></span>

<span data-ttu-id="34f43-120">지원되지 않는 문자는 일반적으로 다른 응용 프로그램(예: Microsoft Word 또는 Microsoft Excel)에서 쿼리나 쿼리 부분을 복사하여 콘텐츠 검색의 쿼리 페이지의 키워드 상자에 붙여 넣는 경우 쿼리에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="34f43-120">Unsupported characters are typically added to a query when you copy the query or parts of the query from other applications (such as Microsoft Word or Microsoft Excel) and paste them in the keyword box on the query page of a Content Search.</span></span> <span data-ttu-id="34f43-121">검색되지 않는 문자를 방지하는 가장 좋은 방법은 키워드 상자에 쿼리를 입력하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="34f43-121">The best way to prevent unsupported characters is to just type the query in the keyword box.</span></span> <span data-ttu-id="34f43-122">또는 Word에서 쿼리를 복사하거나 Excel Microsoft 2013과 같은 일반 텍스트 편집기에서 붙여넣을 메모장.</span><span class="sxs-lookup"><span data-stu-id="34f43-122">Or you can copy a query from Word or Excel, and then paste it in a plain text editor, such as Microsoft Notepad.</span></span> <span data-ttu-id="34f43-123">텍스트 파일을 저장하고 인코딩  드롭다운 목록에서 **ANSI를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="34f43-123">Save the text file and select **ANSI** in the **Encoding** drop-down list.</span></span> <span data-ttu-id="34f43-124">그러면 서식과 지원되지 않는 문자가 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="34f43-124">This will remove any formatting and unsupported characters.</span></span> <span data-ttu-id="34f43-125">그런 다음 텍스트 파일에서 키워드 쿼리 상자에 쿼리를 복사하여 붙여넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34f43-125">Then you can copy and paste the query from the text file to the keyword query box.</span></span>
