---
title: DLP(데이터 손실 방지) 기능이 찾아보는 기능
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
recommendations: false
description: DLP(데이터 손실 방지) 함수가 찾아보는 내용을 살펴 봐야 합니다.
ms.openlocfilehash: 94e7ec97083a8e914ba2155d087d1c7820336805
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60201784"
---
# <a name="what-the-dlp-functions-look-for"></a>DLP 기능이 찾는 항목

DLP(데이터 손실 방지) 정책은 중요한 정보 유형을 사용하여 중요한 항목을 식별할 수 있습니다. 중요한 정보 유형의 예로는 신용 카드 번호와 유럽 직불 카드 번호가 있습니다. 중요한 정보 유형은 특정 패턴을 검색합니다. 중요한 정보 유형은 형식, 체크 체크 인을 확인하여 데이터의 유효성을 검사하고 관련 키워드 또는 기타 정보를 검색합니다. 이 기능 중 일부는 내부 함수에 의해 수행됩니다. 예를 들어 신용 카드 번호 중요한 정보 유형은 함수를 사용하여 만료 날짜와 같은 형식의 날짜를 봐야 합니다. 이 경우 번호가 신용 카드 번호로 보급되는 데 도움이 됩니다.

이 문서에서는 미리 정의한 중요한 정보 유형이 작동되는 방법을 이해하는 데 도움이 되는 이러한 함수가 무엇을 찾아야 하는지 설명하고 있습니다. 자세한 내용은 중요한 정보 [유형 엔터티 정의를 참조하세요.](sensitive-information-type-entity-definitions.md)

## <a name="table-of-functions"></a>함수 표

<br>

****

|함수 이름|함수 동작|은 유효성 검사기입니다.|
|---|---|:---:|
|Func_Argentina_Unique_Tax_Key|아르헨티나 고유 세금 키 감지 및 유효성 검사|아니요|
|Func_aba_routing|ABA 라우팅 번호 검색|예|
|Func_alabama_drivers_license_number|Alabama 드라이버의 라이선스 번호 검색|아니요|
|Func_alaska_delaware_oregon_drivers_license_number|Alaska, Delaware, Oregon 운전 면허 번호 감지|아니요|
|Func_alaska_drivers_license_number|Alaska 운전 면허 번호 검색|아니요|
|Func_alberta_drivers_license_number|Alberta 운전 면허 번호 검색|아니요|
|Func_Argentina_Unique_Tax_Key|아르헨티나 고유 세금 키 검색|아니요|
|Func_arizona_drivers_license_number|Arizona 운전 면허 번호 감지|아니요|
|Func_arkansas_drivers_license_number|Arkansas 운전 면허 번호 검색|아니요|
|Func_australian_business_number|오스트레일리아 비즈니스 번호 검색|아니요|
|Func_Australian_Company_Number|오스트레일리아 회사 번호 검색|아니요|
|Func_australian_medical_account_number|오스트레일리아 의료 계정 번호 감지|아니요|
|Func_australian_tax_file_number|오스트레일리아 세금 파일 번호 검색|예|
|Func_austria_eu_ssn_or_equivalent|오스트리아 사회 보장 번호 감지|아니요|
|Func_austria_eu_tax_file_number|오스트리아 세금 파일 번호 검색|아니요|
|Func_Austria_Value_Added_Tax|오스트리아 부가가치세 감지|아니요|
|Func_belgium_national_number|벨기에 국가 번호 감지|아니요|
|Func_belgium_value_added_tax_number|벨기에 부가가치세 번호 감지|아니요|
|Func_brazil_cnpj|브라질 법적 엔터티 번호(CNPJ) 검색|예|
|Func_brazil_cpf|브라질 CPF 검색|예|
|Func_brazil_rg|브라질 RG 검색|아니요|
|Func_british_columbia_drivers_license_number|British Columbia 운전 면허 번호 감지|아니요|
|Func_bulgaria_eu_national_id_card|불가리아 유니폼 내선 번호 감지|아니요|
|Func_california_drivers_license_number|캘리포니아 운전 면허 번호 감지|아니요|
|Func_canadian_sin|캐나다 죄 감지|예|
|Func_chile_id_card|칠레 ID 카드 검색|아니요|
|Func_china_resident_id|중국 거주 ID 검색|아니요|
|Func_colorado_drivers_license_number|Colorado 운전 면허 번호 감지|아니요|
|Func_connecticut_drivers_license_number|Connecticut 드라이버의 라이선스 번호를 검색합니다.|아니요|
|Func_credit_card|신용 카드 검색|예|
|Func_croatia_id_card|크로아티아 ID 카드 검색|아니요|
|Func_croatia_oib_number|크로아티아 OIB 번호 검색|아니요|
|Func_cyprus_eu_tax_file_number|키프로스 세금 파일 번호 검색|아니요|
|Func_czech_id_card|체코 ID 카드를 검색합니다.|아니요|
|Func_czech_id_card_new_format|체코 ID 카드를 새 형식으로 검색|아니요|
|Func_dea_number|DEA 번호 검색|예|
|Func_denmark_eu_tax_file_number|덴마크 개인 식별 번호 검색|아니요|
|Func_district_of_columbia_drivers_license_number|콜롬비아 구역 운전 면허 번호 감지|아니요|
|Func_estonia_eu_national_id_card|에스토니아 개인 식별 코드 감지|아니요|
|Func_eu_debit_card|유럽 직불 카드 감지|아니요|
|Func_finnish_national_id|핀란드 국가 ID 검색|아니요|
|Func_florida_drivers_license_number|Florida 운전 면허 번호 감지|아니요|
|Func_florida_maryland_michigan_minnesota_drivers_license_number|플로리다, 메릴랜드, 미시간, 미네소타 주 미네소타 운전 면허 번호 감지|아니요|
|Func_formatted_itin|서식 있는 미국 ITIN 검색|예|
|Func_fr_insee|프랑스 INSEE 감지|아니요|
|Func_fr_passport|프랑스 여권 감지|아니요|
|Func_france_eu_tax_file_number|프랑스 세금 파일 번호 검색|아니요|
|Func_france_value_added_tax_number|프랑스 부가가치세 번호 검색|아니요|
|Func_french_drivers_license|프랑스 운전 면허증 감지|아니요|
|Func_french_insee|프랑스어 INSEE 감지|아니요|
|Func_georgia_drivers_license_number|조지아 운전 면허 번호 감지|아니요|
|Func_german_drivers_license|독일 운전 면허증 감지|아니요|
|Func_german_passport|독일 여권 감지|아니요|
|Func_german_passport_data|독일 여권 감지|아니요|
|Func_germany_eu_tax_file_number|독일 세금 파일 번호 검색|아니요|
|Func_germany_value_added_tax_number|독일 부가가치세 번호 감지|아니요|
|Func_greece_eu_ssn|그리스 죄(AMKA) 감지|아니요|
|Func_hawaii_drivers_license_number|하와이 운전 면허 번호 감지|아니요|
|Func_hong_kong_id_card|홍콩 ID 카드 감지|아니요|
|Func_hungarian_value_added_tax_number|헝가리 값 추가 세금 번호 검색|아니요|
|Func_hungary_eu_national_id_card|헝가리 개인식별번호 검색|아니요|
|Func_hungary_eu_ssn_or_equivalent|헝가리 사회 보장 번호 검색|아니요|
|Func_hungary_eu_tax_file_number|헝가리 세금 파일 번호 검색|아니요|
|Func_iban|IBAN 감지|예|
|Func_idaho_drivers_license_number|Idaho 운전 면허 번호 검색|아니요|
|Func_illinois_drivers_license_number|일리노이 운전 면허 번호 검색|아니요|
|Func_india_aadhaar|인도 아도하르 감지|예|
|Func_indiana_drivers_license_number|인도 운전 면허 번호 감지|아니요|
|Func_iowa_drivers_license_number|Iowa 운전 면허 번호 감지|아니요|
|Func_ireland_pps|아일랜드 PPS 감지|아니요|
|Func_israeli_national_id_number|이스라엘 국가 ID 번호 감지|아니요|
|Func_italy_eu_national_id_card|이탈리아 회계 코드 감지|아니요|
|Func_italy_value_added_tax_number|이탈리아 부가가치세 번호 감지|아니요|
|Func_japanese_my_number_corporate|일본 내 번호 회사 검색|예|
|Func_japanese_my_number_personal|일본 내 번호 개인 검색|예|
|Func_jp_bank_account|일본 은행 계좌 검색|아니요|
|Func_jp_bank_account_branch_code|일본 은행 계좌 분기 코드 검색|아니요|
|Func_jp_drivers_license_number|일본 운전 면허 번호 감지|아니요|
|Func_jp_passport|일본 여권 감지|아니요|
|Func_jp_resident_registration_number|일본 거주 등록 번호 검색|아니요|
|Func_jp_sin|일본 SIN 감지|아니요|
|Func_jp_sin_pre_1997|1997년 일본 sin pre 1997 감지|아니요|
|Func_kansas_drivers_license_number|Kansas 운전 면허 번호 검색|아니요|
|Func_kentucky_drivers_license_number|킷킷 드라이버의 라이선스 번호 검색|아니요|
|Func_kentucky_massachusetts_virginia_drivers_license_number|버지니아주 킷키, 매사추세츠 주, 버지니아 운전 면허 번호 감지|아니요|
|Func_latvia_eu_national_id_card|라트비아 개인 코드 감지|아니요|
|Func_lithuania_eu_tax_file_number|리투아니아 개인 코드 감지|아니요|
|Func_louisiana_drivers_license_number|루이지애나 운전 면허 번호 감지|아니요|
|Func_luxemburg_eu_tax_file_number|룩세르버그 국가 ID 번호(자연인)를 검색합니다.|아니요|
|Func_luxemburg_eu_tax_file_number_non_natural|룩세르버그 국가 ID 번호(자연인이 아닌 사람) 검색|아니요|
|Func_maine_drivers_license_number|Maine 드라이버의 라이선스 번호를 검색합니다.|아니요|
|Func_manitoba_drivers_license_number|매니토바 운전 면허 번호 검색|아니요|
|Func_maryland_drivers_license_number|Maryland 운전 면허 번호 감지|아니요|
|Func_massachusetts_drivers_license_number|Massachusetts 드라이버의 라이선스 번호 감지|아니요|
|Func_mexico_population_registry_code|멕시코 인구 레지스트리 코드 감지|아니요|
|Func_michigan_minnesota_drivers_license_number|미주건, 미네소타 운전 면허 번호 감지|아니요|
|Func_minnesota_drivers_license_number|미네소타 운전 면허 번호 검색|아니요|
|Func_mississippi_oklahoma_drivers_license_number|Mississippi, Oklahoma driver's license number를 검색합니다.|아니요|
|Func_missouri_drivers_license_number|미주리 운전 면허 번호 감지|아니요|
|Func_montana_drivers_license_number|몬타나 운전 면허 번호 감지|아니요|
|Func_nebraska_drivers_license_number|Nebraska 운전 면허 번호 검색|아니요|
|Func_netherlands_bsn|네덜란드 BSN 감지|아니요|
|Func_netherlands_eu_tax_file_number|네덜란드 세금 파일 번호 검색|아니요|
|Func_netherlands_value_added_tax_number|네덜란드 부가가치세 번호 검색|아니요|
|Func_nevada_drivers_license_number|Nevada 운전 면허 번호 검색|아니요|
|Func_new_brunswick_drivers_license_number|새 Brunswick 드라이버의 라이선스 번호를 검색합니다.|아니요|
|Func_new_hampshire_drivers_license_number|새 Hampshire 운전 면허 번호 검색|아니요|
|Func_new_jersey_drivers_license_number|새 저지 운전 면허 번호 검색|아니요|
|Func_new_mexico_drivers_license_number|멕시코 운전 면허 번호 감지|아니요|
|Func_new_york_drivers_license_number|뉴욕 운전 면허 번호 검색|아니요|
|Func_new_zealand_bank_account_number|뉴질랜드 은행 계좌 번호 검색|아니요|
|Func_new_zealand_inland_revenue_number|뉴질랜드 내륙 수익 번호 감지|아니요|
|Func_new_zealand_ministry_of_health_number|뉴질랜드 보건부 보건부를 감지합니다.|아니요|
|Func_newfoundland_labrador_drivers_license_number|Newfoundland Labrador 드라이버의 라이선스 번호를 검색합니다.|아니요|
|Func_newzealand_driver_license_number|뉴질랜드 운전 면허 번호 감지|아니요|
|Func_newzealand_social_welfare_number|뉴질랜드 사회 일지 번호 감지|아니요|
|Func_north_carolina_drivers_license_number|North Carolina 운전 면허 번호 감지|아니요|
|Func_north_dakota_drivers_license_number|North Dakota 운전 면허 번호 검색|아니요|
|Func_norway_id_number|노르웨이 ID 번호 검색|아니요|
|Func_nova_scotia_drivers_license_number|Nova Scotia 운전 면허 번호 검색|아니요|
|Func_ohio_drivers_license_number|Ohio 드라이버의 라이선스 번호 감지|아니요|
|Func_ontario_drivers_license_number|Ontario 드라이버의 라이선스 번호 검색|아니요|
|Func_pennsylvania_drivers_license_number|Pennsylvania 운전 면허 번호 감지|아니요|
|Func_pesel_identification_number|폴란드 국가 ID(PESEL) 검색|아니요|
|Func_poland_eu_tax_file_number|폴란드 세금 파일 번호 검색|아니요|
|Func_polish_national_id|폴란드 ID 카드 검색|아니요|
|Func_polish_passport_number|폴란드 여권 번호 감지|아니요|
|Func_polish_regon_number|폴란드어 REGON 번호를 검색합니다.|아니요|
|Func_portugal_eu_tax_file_number|포르투갈 세금 식별 번호 검색|아니요|
|Func_prince_edward_island_drivers_license_number|에드워드아일랜드 운전 면허 번호 감지|아니요|
|Func_quebec_drivers_license_number|Quebec 드라이버의 라이선스 번호 검색|아니요|
|Func_randomized_formatted_ssn|임의로 서식이 지정된 미국 SSN 검색|예|
|Func_randomized_unformatted_ssn|임의로 변형되지 않은 미국 SSN 감지|예|
|Func_rhode_island_drivers_license_number|로데 섬 운전 면허 번호 감지|아니요|
|Func_romania_eu_national_id_card|루마니아 CNP(개인 숫자 코드) 검색|아니요|
|Func_saskatchewan_drivers_license_number|Saskatchewan 운전 면허 번호 검색|아니요|
|Func_slovakia_eu_national_id_card|슬로바키아 개인 번호 감지|아니요|
|Func_slovenia_eu_national_id_card|Slovenia Unique Master Citizen Number 검색|아니요|
|Func_slovenia_eu_tax_file_number|Slovenia 세금 파일 번호 검색|아니요|
|Func_south_africa_identification_number|남아프리카 공화국 ID 번호 감지|예|
|Func_south_carolina_drivers_license_number|South Carolina 운전 면허 번호 감지|아니요|
|Func_south_dakota_drivers_license_number|South Dakota 운전 면허 번호 검색|아니요|
|Func_south_korea_resident_number|대한민국 거주자 번호 검색|아니요|
|Func_spain_eu_DL_and_NI_number_citizen|스페인 DL 및 NI 번호 시민 감지|아니요|
|Func_spain_eu_DL_and_NI_number_foreigner|스페인 DL 및 NI 번호 외래인 검색|아니요|
|Func_spain_eu_driver s_license_number|스페인 운전 면허 번호 감지|아니요|
|Func_spain_eu_tax_file_number|스페인 세금 파일 번호 검색|아니요|
|Func_spanish_social_security_number|스페인어 사회 보장 번호 감지|아니요|
|Func_ssn|임의로 지정되지 않은 미국 SSN을 검색하는 함수|예|
|Func_sweden_eu_tax_file_number|스웨덴 세금 파일 번호 검색|아니요|
|Func_swedish_national_identifier|스웨덴어 국가 식별자 검색|예|
|Func_swiss_social_security_number_ahv|스위스 사회 보장 번호 AHV 검색|아니요|
|Func_taiwanese_national_id|대만 국가 ID 검색|아니요|
|Func_tennessee_drivers_license_number|테넌트 운전 면허 번호 검색|아니요|
|Func_texas_drivers_license_number|텍사스 운전 면허 번호 검색|아니요|
|Func_Thai_Citizen_Id|태국 시민 ID 감지|아니요|
|Func_Turkish_National_Id|터키어 국가 ID 검색|예|
|Func_uk_drivers_license|영국 운전 면허를 검색합니다.|아니요|
|Func_uk_eu_tax_file_number|영국 고유 납세자 번호 검색|아니요|
|Func_uk_nhs_number|영국 NHS 번호 검색|예|
|Func_uk_nino|UK NINO 감지|아니요|
|Func_unformatted_canadian_sin|무형 캐나다 SIN 검색|아니요|
|Func_unformatted_itin|미국 ITIN의 미포장된 검색|예|
|Func_unformatted_ssn|임의가 없는 미국 SSN 감지|예|
|Func_usa_uk_passport|미국 및 영국 여권 감지|예|
|Func_utah_drivers_license_number|유타 운전 면허 번호 검색|아니요|
|Func_vermont_drivers_license_number|Vermont 드라이버의 라이선스 번호 검색|아니요|
|Func_virginia_drivers_license_number|버지니아 운전 면허 번호 감지|아니요|
|Func_washington_drivers_license_number|워싱턴 운전 면허 번호 감지|아니요|
|Func_west_virginia_drivers_license_number|서부 버지니아 운전 면허 번호 감지|아니요|
|Func_wisconsin_drivers_license_number|Wisconsin 드라이버의 라이선스 번호 검색|아니요|
|Func_wyoming_drivers_license_number|Wyoming 드라이버의 라이선스 번호 감지|아니요|
|

## <a name="func_us_date"></a>Func_us_date

Func_us_date 미국 형식의 날짜를 선택합니다. 일반적인 형식은 "월/일/년", "월-일-년" 및 "월 일 년"입니다. 월 이름이나 약어는 대소문자 구분이 없습니다.

예제:

- 2016년 12월 2일
- 2016년 12월 2일
- dec 02 2016
- 12/2/2016
- 12/02/16
- 2016년 12월 2일
- 12-2-16

허용되는 월 이름:

- 영어
  - 1월, 2월, 3월, 4월, 6월, 7월, 8월, 9월, 10월, 11월, 12월
  - Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.

## <a name="func_eu_date"></a>Func_eu_date

Fund_eu_dates looks for dates in common E.U. "일/월/년", "일-월-년" 및 "일 월 연도"와 같은 형식(및 대부분의 위치가 미국 이외 지역)입니다. 월 이름이나 약어는 대소문자 구분이 없습니다.

예제:

- 22 Dec 2016
- 2016년 12월 2일
- 2 Dec 16
- 2/12/2016
- 02/12/16
- 2016년 12월 2일
- 2-12-16

허용되는 월 이름:

- 영어
  - 1월, 2월, 3월, 4월, 6월, 7월, 8월, 9월, 10월, 11월, 12월
  - Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.
- 네덜란드어
  - januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December
  - jan feb maart apr mei jun jul aug sep sept oct okt nov dec
- 프랑스어
  - janvier, février, mars, avril, mai, juin juillet, août, septembre, octobre, novembre, décembre
  - janv. févr. mars avril mai juin juil. août. oct. nov. déc.
- 독일어
  - jänuar, februar, märz, April, mai, juni juli, August, September, oktober, November, dezember
  - Jan./Jän. Feb. März Apr. Mai Juni Juli Aug. Sept. Okt. 11월 Dez.
- 이탈리아어
  - gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre
  - genn. febbr. mar. apr. magg. giugno luglio ag. sett. ott. nov. dic.
- 포르투갈어
  - janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro
  - jan fev mar abr mai jun jul ago set out nov dez
- 스페인어
  - enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre
  - enero feb. marzo abr. mayo jun. jul. agosto sept./set. oct. nov. dic.

## <a name="func_eu_date1-deprecated"></a>Func_eu_date1(더 이상 사용되지 않음)

> [!NOTE]
> 이 함수는 현재 위의 함수에 포함된 포르투갈어 월 이름만 지원하기 때문에 더 이상  `Func_eu_date` 사용하지 않습니다.

이 함수는 포르투갈어에서 일반적으로 사용되는 형식의 날짜를 찾습니다. 이 함수의 형식은 의 형식과 동일합니다. 사용되는  `Func_eu_date` 언어에서만 다릅니다.

예제:

- 2 Dez 2016
- 02 dez 2016
- 2 Dez 16
- 2/12/2016
- 02/12/16
- 2-Dez-2016
- 2-12-16

허용되는 월 이름:

- 포르투갈어
  - janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro
  - jan fev mar abr mai jun jul ago set out nov dez

## <a name="func_eu_date2-deprecated"></a>Func_eu_date2(더 이상 사용되지 않음)

> [!NOTE]
> 이 함수는 현재 위의 함수에 포함된 네덜란드어 월 이름만 지원하기 때문에 더 이상  `Func_eu_date` 사용하지 않습니다.

이 함수는 네덜란드어에서 일반적으로 사용되는 형식의 날짜를 찾습니다. 이 함수의 형식은 의 형식과 동일합니다. 사용되는  `Func_eu_date` 언어에서만 다릅니다.

예제:

- 2 Mei 2016
- 02 mei 2016
- 2 Mei 16
- 2/12/2016
- 02/12/16
- 2-Mei-2016
- 2-12-16

허용되는 월 이름:

- 네덜란드어
  - januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December
  - jan feb maart apr mei jun jul aug sep sept out okt nov dec

## <a name="func_expiration_date"></a>Func_expiration_date

Func_expiration_date 신용 카드 및 직불 카드에서 일반적으로 사용되는 형식의 날짜를 선택합니다. 이 함수는 "월/년", "월-년", "[월 이름] 년" 및 "[월 약어] 년" 형식의 날짜와 일치합니다. 월 이름이나 약어는 대소문자 구분이 없습니다.

예제:

- MM/YY - 예를 들어 01/11 또는 1/11
- MM/YYYY - 예를 들어 01/2011, 1/2011 등
- MM-YY -- 예를 들어 01-22 또는 1-11
- MM-YYYY -- 예를 들어 01-2000 또는 1-2000

다음 형식은 YY 또는 YYYY를 지원합니다.

- Month-YYYY -- 예: Jan-2010 또는 january-2010, Jan-10 또는 january-10
- Month YYYY -- 예를 들어 'january 2010', 'Jan 2010', 'january 10' 또는 'Jan 10'
- MonthYYYY -- 예를 들어 'january2010', 'Jan2010', 'january10' 또는 'Jan10'
- Month/YYYY -- 예를 들어 'january/2010' 또는 'Jan/2010' 또는 'january/10' 또는 'Jan/10'

허용되는 월 이름:

- 영어
  - 1월, 2월, 3월, 4월, 6월, 7월, 8월, 9월, 10월, 11월, 12월
  - Jan Feb Mar Apr May June July Aug Sept Oct Nov Dec

## <a name="func_us_address"></a>Func_us_address

Func_us_address 미국 주 이름 또는 우편 약어와 유효한 우편 번호가 함께 표시됩니다. 우편 번호는 미국 주 이름 또는 약어와 관련된 올바른 우편 번호 중 하나여야 합니다. 미국 주 이름과 우편 번호를 문장 부호나 문자로 구분할 수 없습니다.

예제:

- Washington 98052
- Washington 98052-9998
- WA 98052
- WA 98052-9998
