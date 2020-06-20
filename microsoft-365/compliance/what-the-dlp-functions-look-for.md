---
title: DLP 기능이 찾는 항목
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/18/2016
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: 미리 정의 된 중요 한 정보 유형의 작동 방식을 이해 하는 데 도움이 되도록 DLP (데이터 손실 방지) 함수가 찾는 내용을 알아봅니다.
ms.openlocfilehash: 838277b2e30696cd00cfc30df49c1d5a29149d92
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819278"
---
# <a name="what-the-dlp-functions-look-for"></a>DLP 기능이 찾는 항목

Data loss prevention (DLP) includes sensitive information types, such as Credit Card Number and EU Debit Card Number, which are ready for you to use in your DLP policies. These sensitive information types look for a specific pattern and corroborate it by ensuring proper formatting, enforcing checksums, and looking for relevant keywords or other information. Some of this functionality is performed by internal functions. For example, the Credit Card Number sensitive information type uses a function to look for dates formatted like an expiration date, to help corroborate that a number is a credit card number.
  
이 항목에는 이러한 함수가 찾는 대상이 설명되어 있어 미리 정의된 중요한 정보 유형이 작동하는 방식을 이해할 수 있습니다. 자세한 내용은 [중요 한 정보 유형 엔터티 정의](sensitive-information-type-entity-definitions.md) 를 참조 하세요.
  
## <a name="func_us_date"></a>Func_us_date

이 함수는 미국에서 일반적으로 사용 되는 형식으로 날짜를 찾습니다. 여기에는 "월/일/년", "월-일-년" 및 "월 일 년" 형식이 포함 됩니다. 월 이름 또는 약어는 대/소문자를 구분하지 않습니다. 
  
예제:
  
- 2016 년 12 월 2 일
    
- 12 월 2 일 2016
    
- dec 02 2016
    
- 12/2/2016
    
- 12/02/16
    
- 2-2016 년 12 월
    
- 12-2-16
    
허용되는 월 이름:
  
- English
    
  - 1 월, 2 월, 3 월, 4 월, 5 월, 01 년 6 월, 년 9 월, 10 월, 년 11 월, 12 월
    
  - 1 월 2 월 3 월 4 일. c a 11 월호-2005 년 12 월.
    
## <a name="func_eu_date"></a>Func_eu_date

This function looks for a date in the format commonly used in the E.U. (and most places outside the U.S.). This includes the formats "day/month/year", "day-month-year", and "day month year". The names or abbreviations of months are not case sensitive.
  
예제:
  
- 2 월 12 일 2016
    
- 02 년 12 월 2016
    
- 2 월 16 일
    
- 2/12/2016
    
- 02/12/16
    
- 2016 년 12 월 2 일
    
- 2-12-16
    
허용되는 월 이름:
  
- English
    
  - 1 월, 2 월, 3 월, 4 월, 5 월, 01 년 6 월, 년 9 월, 10 월, 년 11 월, 12 월
    
  - 1 월 2 월 3 월 4 일. c a 11 월호-2005 년 12 월.
    
- Dutch
    
  - januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December
    
  - jan 1 월 maart 년 9 월 8 일
    
- French
    
  - janvier, février, mars, avril, mai, juin juillet, août, septembre, octobre, novembre, décembre
    
  - janv. févr. mars avril mai juin juil août 9 월 일. 수정일. déc.
    
- German
    
  - jänuar, februar, märz, 4 월, mai, juni juli, 8 월, 09, oktober, 11 월, dezember
    
  - 1 월/Jän. März Apr. Mai Juni Juli 8 ~ 9. Okt 11 월.
    
- Italian
    
  - gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, novembre
    
  - genn febbr mar. 년. magg. giugno luglio ag sett ott. 수정일. home.dic.
    
- 포르투갈어
    
  - janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro
    
  - 1 월의 fev mar abr mai 6 월 30 일 전인 11 월 이전 설정
    
- Spanish
    
  - enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre
    
  - enero 년 2 월 marzo abr mayo의 6 월 최종. agosto/set. 일. 수정일. home.dic.
    
## <a name="func_eu_date1-deprecated"></a>Func_eu_date1(더 이상 사용되지 않음)

> [!NOTE]
> 이 함수는 이제 위의 함수에 포함 되는 포르투갈어 월 이름을 지원 하기 때문에 더 이상 사용 되지 않습니다 `Func_eu_date` . 
  
이 함수는 포르투갈어에서 일반적으로 사용되는 형식의 날짜를 찾습니다. 이 함수의 형식은 `Func_eu_date` 사용 되는 언어에만 다른 것과 동일 합니다.
  
예제:
  
- 2 dez 2016
    
- 02 dez 2016
    
- 2 dez 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-dez-2016
    
- 2-12-16
    
허용되는 월 이름:
  
- 포르투갈어
    
  - janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro
    
  - 1 월의 fev mar abr mai 6 월 30 일 전인 11 월 이전 설정
    
## <a name="func_eu_date2-deprecated"></a>Func_eu_date2(더 이상 사용되지 않음)

> [!NOTE]
> 이 함수는 이제 위의 함수에 포함 되는 네덜란드어 월 이름만 지원 하기 때문에 더 이상 사용 되지 않습니다 `Func_eu_date` . 
  
이 함수는 네덜란드어에서 일반적으로 사용되는 형식의 날짜를 찾습니다. 이 함수의 형식은 `Func_eu_date` 사용 되는 언어에만 다른 것과 동일 합니다.
  
예제:
  
- 2 mei 2016
    
- 02 mei 2016
    
- 2 mei 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-mei-2016
    
- 2-12-16
    
허용되는 월 이름:
  
- Dutch
    
  - januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December
    
  - jan 1 월 maart 년 9 월 8 일
    
## <a name="func_expiration_date"></a>Func_expiration_date

이 함수는 신용 카드 및 직불 카드에서 일반적으로 사용되는 형식의 날짜를 찾으며 월 기준의 일은 제외합니다. 이 함수는 "month/year", "month-year", "[month name] year" 및 "[month 약어] year" 형식으로 날짜를 일치 시킵니다. 월 이름 또는 약어는 대/소문자를 구분하지 않습니다.
  
예제:
  
- MM/YY - 예를 들어 01/11 또는 1/11
    
- MM/YYYY - 예를 들어 01/2011, 1/2011 등
    
- MM-YY -- 예를 들어 01-22 또는 1-11
    
- MM-YYYY -- 예를 들어 01-2000 또는 1-2000
    
다음 형식은 YY 또는 YYYY를 지원합니다.
  
- Month-YYYY -- 예를 들어 Jan-2010, january-2010, Jan-10 또는 january-10
    
- Month YYYY -- 예를 들어 'january 2010', 'Jan 2010', 'january 10' 또는 'Jan 10'
    
- MonthYYYY -- 예를 들어 'january2010', 'Jan2010', 'january10' 또는 'Jan10'
    
- Month/YYYY--예를 들어 ' 1 월/2010 ' 또는 ' Jan/2010 ' 또는 ' 1 월/10 '
    
허용되는 월 이름:
  
- English
    
  - 1 월, 2 월, 3 월, 4 월, 5 월, 01 년 6 월, 년 9 월, 10 월, 년 11 월, 12 월
    
  - 1 월 2 월 3 월 4 일, 08 년 6 시 9 월 8 일
    
## <a name="func_us_address"></a>Func_us_address

This function looks for a U.S. state name or postal abbreviation followed by a valid zip code, just as they are used in postal addresses. The zip code must be one of the correct zip codes associated with the U.S. state name or abbreviation. The U.S. state name and zip code cannot be separated by punctuation or letters.
  
예제:
  
- Washington 98052
    
- Washington 98052-9998
    
- WA 98052
    
- WA 98052-9998
    

