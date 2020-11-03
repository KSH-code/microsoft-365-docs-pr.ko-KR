---
title: DLP (데이터 손실 방지) 함수에서 찾을 대상
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
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
description: DLP (데이터 손실 방지) 함수에서 찾는 사항에 대해 알아봅니다.
ms.openlocfilehash: b77075b0b31ad5d6e6e2b7062c35e96649fa8365
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841449"
---
# <a name="what-the-dlp-functions-look-for"></a>DLP 기능이 찾는 항목

DLP (데이터 손실 방지) 정책은 중요 한 정보 유형을 사용 하 여 중요 한 항목을 식별 합니다. 중요 한 정보 유형의 예로는 신용 카드 번호 및 EU 직불 카드 번호가 있습니다. 중요 한 정보 유형은 특정 패턴을 찾습니다. 중요 한 정보 유형은 데이터의 형식을 보고 체크섬을 확인 하 고 관련 키워드 또는 기타 정보를 조사 합니다. 이 기능 중 일부는 내부 함수에 의해 수행됩니다. 예를 들어 신용 카드 번호 중요 한 정보 유형은 함수를 사용 하 여 만료 날짜와 같이 서식이 지정 된 날짜를 찾습니다. 이렇게 하면 숫자가 신용 카드 번호 corroborate 수 있습니다.
  
이 문서에서는 미리 정의 된 중요 한 정보 유형의 작동 방식을 이해 하는 데 도움이 되도록 이러한 함수가 찾는 항목에 대해 설명 합니다. 자세한 내용은 [중요 한 정보 유형 엔터티 정의](sensitive-information-type-entity-definitions.md) 를 참조 하세요.
  
## <a name="table-of-functions"></a>함수 표

|함수 이름  |함수 작업  |유효성 검사기|
|---------|---------|---------|
|Func_Argentina_Unique_Tax_Key|아르헨티나 고유 세금 키 검색 및 유효성 검사|아니요|
|Func_aba_routing|ABA 라우팅 번호 검색| 예|
|Func_alabama_drivers_license_number|앨라배마 운전 면허 번호 검색|아니요|
|Func_alaska_delaware_oregon_drivers_license_number|알래스카, Delaware, Oregon 운전 면허 번호를 검색 합니다.|아니요|
|Func_alaska_drivers_license_number|알래스카 운전 면허 번호를 감지 합니다.|아니요|
|Func_alberta_drivers_license_number|앨버타 운전 면허 번호 검색|아니요|
|Func_Argentina_Unique_Tax_Key|아르헨티나 고유 세금 키 검색|아니요|
|Func_arizona_drivers_license_number|애리조나 운전 면허 번호 검색|아니요|
|Func_arkansas_drivers_license_number|Arkansas 운전 면허 번호 검색|아니요|
|Func_australian_business_number|오스트레일리아 근무지 번호 검색|아니요|
|Func_Australian_Company_Number|오스트레일리아 회사 번호 검색|아니요|
|Func_australian_medical_account_number|호주 의료 계좌 번호 검색|아니요|
|Func_australian_tax_file_number|오스트레일리아 세금 파일 번호 검색|예|
|Func_austria_eu_ssn_or_equivalent|오스트리아 주민 등록 번호 검색|아니요|
|Func_austria_eu_tax_file_number|오스트리아 세금 파일 번호 검색|아니요|
|Func_Austria_Value_Added_Tax|오스트리아 값 추가 됨 검색|아니요|
|Func_belgium_national_number|벨기에 국가 번호 검색|아니요|
|Func_belgium_value_added_tax_number|벨기에 값 추가 세금 번호를 감지 합니다.|아니요|
|Func_brazil_cnpj|브라질 legal 엔티티 번호 (CNPJ)를 검색 합니다.|예|
|Func_brazil_cpf|브라질 CPF 검색|예|
|Func_brazil_rg|브라질 RG 검색|아니요|
|Func_british_columbia_drivers_license_number|영국령 콜롬비아 운전 면허 번호를 감지 합니다.|아니요|
|Func_bulgaria_eu_national_id_card|불가리아 uniform 민사 번호 검색|아니요|
|Func_california_drivers_license_number|캘리포니아 운전 면허 번호를 감지 합니다.|아니요|
|Func_canadian_sin|캐나다 사인 검색|예|
|Func_chile_id_card|칠레 ID 카드 검색|아니요|
|Func_china_resident_id|중국 상주 ID 검색|아니요|
|Func_colorado_drivers_license_number|Colorado 운전 면허 번호 검색|아니요|
|Func_connecticut_drivers_license_number|Connecticut 운전 면허 번호 검색|아니요|
|Func_credit_card|신용 카드 검색|예|아니요|
|Func_croatia_id_card|크로아티아 ID 카드 검색|아니요|
|Func_croatia_oib_number|크로아티아 OIB 번호 검색|아니요|
|Func_cyprus_eu_tax_file_number|키프로스 세금 파일 번호 검색|아니요|
|Func_czech_id_card|체코어 ID 카드 검색|아니요|
|Func_czech_id_card_new_format|체코어 ID 카드를 새 형식으로 검색 합니다.|아니요|
|Func_dea_number|DEA 번호 검색|예|
|Func_denmark_eu_tax_file_number|덴마크 개인 식별 번호 검색|아니요|
|Func_district_of_columbia_drivers_license_number|콜롬비아 운전 면허 번호의 학구를 감지 합니다.|아니요|
|Func_estonia_eu_national_id_card|에스토니아 개인 식별 코드 검색|아니요|
|Func_eu_debit_card|EU 직불 카드 검색|아니요|
|Func_finnish_national_id|핀란드어 국가 ID 검색|아니요|
|Func_florida_drivers_license_number|Florida 운전 면허 번호 검색|아니요|
|Func_florida_maryland_michigan_minnesota_drivers_license_number|Florida, 메릴랜드 주, Michigan, Minnesota 운전 면허 번호 검색|아니요|
|Func_formatted_itin|서식이 지정 된 US ITIN 검색|예|
|Func_fr_insee|프랑스 INSEE 검색|아니요|
|Func_fr_passport|프랑스 여권 검색|아니요|
|Func_france_eu_tax_file_number|프랑스 세금 파일 번호 검색|아니요|
|Func_france_value_added_tax_number|프랑스 값 추가 된 세금 번호를 검색 합니다.|아니요|
|Func_french_drivers_license|프랑스어 드라이버의 라이선스 검색|아니요|
|Func_french_insee|프랑스 INSEE 검색|아니요|
|Func_georgia_drivers_license_number|그루지야 운전 면허 번호를 감지 합니다.|아니요|
|Func_german_drivers_license|독일 운전 면허를 감지 합니다.|아니요|
|Func_german_passport|독일 여권 감지|아니요|
|Func_german_passport_data|독일 여권 감지|아니요|
|Func_germany_eu_tax_file_number|독일 세금 파일 번호 검색|아니요|
|Func_germany_value_added_tax_number|독일 검색 값 추가 세금 번호|아니요|
|Func_greece_eu_ssn|그리스 사인 검색 (AMKA)|아니요|
|Func_hawaii_drivers_license_number|하와이 운전 면허 번호를 감지 합니다.|아니요|
|Func_hong_kong_id_card |홍콩 ID 카드 검색|아니요|
|Func_hungarian_value_added_tax_number|헝가리어 값에 추가 된 세금 번호를 감지 합니다.|아니요|
|Func_hungary_eu_national_id_card|헝가리어 개인 식별 번호를 검색 합니다.|아니요|
|Func_hungary_eu_ssn_or_equivalent|헝가리어 주민 등록 번호 검색|아니요|
|Func_hungary_eu_tax_file_number|헝가리어 세금 파일 번호 검색|아니요|
|Func_iban|IBAN를 검색 합니다.|예|
|Func_idaho_drivers_license_number|Idaho 운전 면허 번호를 감지 합니다.|아니요|
|Func_illinois_drivers_license_number|Illinois 운전 면허 번호 검색|아니요|
|Func_india_aadhaar|인도 aadhaar|예|
|Func_indiana_drivers_license_number|인디애나 운전 면허 번호를 감지 합니다.|아니요|
|Func_iowa_drivers_license_number|Iowa 운전 면허 번호 검색|아니요|
|Func_ireland_pps|아일랜드 PPS 감지|아니요|
|Func_israeli_national_id_number|이스라엘 국가 ID 번호 검색|아니요|
|Func_italy_eu_national_id_card |이탈리아 회계 코드 검색|아니요|
|Func_italy_value_added_tax_number|이탈리아 값이 추가 된 세금 번호를 감지 합니다.|아니요|
|Func_japanese_my_number_corporate|일본 내 번호 검색 회사|예|
|Func_japanese_my_number_personal|일본 내 번호 개인 검색|예|
|Func_jp_bank_account|일본 은행 계좌 검색|아니요|
|Func_jp_bank_account_branch_code|일본 뱅크 계정 분기 코드를 검색 합니다.|아니요|
|Func_jp_drivers_license_number|일본 운전 면허 번호를 감지 합니다.|아니요|
|Func_jp_passport|일본 여권 검색|아니요|
|Func_jp_resident_registration_number|일본 상주 등록 번호 검색|아니요|
|Func_jp_sin|일본 사인 검색|아니요|
|Func_jp_sin_pre_1997|일본 사인 이전 1997를 검색 합니다.|아니요|
|Func_kansas_drivers_license_number|Kansas 운전 면허 번호 검색|아니요|
|Func_kentucky_drivers_license_number|켄터키 운전 면허 번호를 감지 합니다.|아니요|
|Func_kentucky_massachusetts_virginia_drivers_license_number|켄터키, Massachusetts, Virginia 운전 면허 번호를 검색 합니다.|아니요|
|Func_latvia_eu_national_id_card|라트비아 개인 코드 검색|아니요|
|Func_lithuania_eu_tax_file_number|리투아니아 개인 코드 검색|아니요|
|Func_louisiana_drivers_license_number|루이지애나 운전 면허 번호 검색|아니요|
|Func_luxemburg_eu_tax_file_number|룩셈부르크 국내 식별 번호 (자연어)를 검색 합니다.|아니요|
|Func_luxemburg_eu_tax_file_number_non_natural|룩셈부르크 국내 식별 번호 (자연어 아님)를 감지 합니다.|아니요|
|Func_maine_drivers_license_number|Maine 운전 면허 번호 검색|아니요|
|Func_manitoba_drivers_license_number|매니토바 운전 면허 번호 검색|아니요|
|Func_maryland_drivers_license_number|메릴랜드 주 운전 면허 번호 검색|아니요|
|Func_massachusetts_drivers_license_number|Massachusetts 운전 면허 번호 검색|아니요|
|Func_mexico_population_registry_code|멕시코 채우기 레지스트리 코드를 검색 합니다.|아니요|
|Func_michigan_minnesota_drivers_license_number|Michigan, Minnesota 운전 면허 번호 검색|아니요|
|Func_minnesota_drivers_license_number|Minnesota 운전 면허 번호 검색|아니요|
|Func_mississippi_oklahoma_drivers_license_number|Mississippi, Oklahoma 드라이버의 라이선스 번호를 검색 합니다.|아니요|
|Func_missouri_drivers_license_number|Missouri 운전 면허 번호 검색|아니요|
|Func_montana_drivers_license_number|Montana 운전 면허 번호 검색|아니요|
|Func_nebraska_drivers_license_number|Nebraska 운전 면허 번호 검색|아니요|
|Func_netherlands_bsn|네덜란드 BSN 검색|아니요|
|Func_netherlands_eu_tax_file_number|네덜란드 세금 파일 번호 검색|아니요|
|Func_netherlands_value_added_tax_number|네덜란드 번호를 검색 합니다.|아니요|
|Func_nevada_drivers_license_number|Nevada 운전 면허 번호 검색|아니요|
|Func_new_brunswick_drivers_license_number|새 뉴브런즈윅 운전 면허 번호 검색|아니요|
|Func_new_hampshire_drivers_license_number|새 Hampshire 운전 면허 번호 검색|아니요|
|Func_new_jersey_drivers_license_number |새 Jersey 운전 면허 번호 검색|아니요|
|Func_new_mexico_drivers_license_number |새 멕시코 운전 면허 번호를 감지 합니다.|아니요|
|Func_new_york_drivers_license_number   |뉴욕 운전 면허 번호 검색|아니요|
|Func_new_zealand_bank_account_number   |새 뉴질랜드 계좌 번호 검색|아니요|
|Func_new_zealand_inland_revenue_number |뉴질랜드 inland 수익 번호를 새로 검색 합니다.|아니요|
|Func_new_zealand_ministry_of_health_number|새 뉴질랜드 보건부 (체력 번호) 검색|아니요|
|Func_newfoundland_labrador_drivers_license_number|뉴펀들랜드 래브라도 운전 면허 번호를 감지 합니다.|아니요|
|Func_newzealand_driver_license_number  |새 뉴질랜드 드라이버 라이선스 번호 검색|아니요|
|Func_newzealand_social_welfare_number  |뉴질랜드 공유 welfare 번호 검색|아니요|
|Func_north_carolina_drivers_license_number|북쪽 Carolina 운전 면허 번호를 감지 합니다.|아니요|
|Func_north_dakota_drivers_license_number|북쪽 Dakota 운전 면허 번호를 감지 합니다.|아니요|
|Func_norway_id_number  |노르웨이 ID 번호를 검색 합니다.|아니요|
|Func_nova_scotia_drivers_license_number|노바스코샤 노바스코샤 운전 면허 번호 검색|아니요|
|Func_ohio_drivers_license_number   |Ohio 운전 면허 번호 검색|아니요|
|Func_ontario_drivers_license_number    |온타리오 운전 면허 번호 검색|아니요|
|Func_pennsylvania_drivers_license_number|Pennsylvania 운전 면허 번호 검색|아니요|
|Func_pesel_identification_number   |PESEL (폴란드 국가 ID)를 검색 합니다.|아니요|
|Func_poland_eu_tax_file_number |폴란드 세금 파일 번호 검색|아니요|
|Func_polish_national_id    |폴란드 id 카드 검색|아니요|
|Func_polish_passport_number    |폴란드어 여권 번호 검색|아니요|
|Func_polish_regon_number   |폴란드어 REGON 번호를 감지 합니다.|아니요|
|Func_portugal_eu_tax_file_number|포르투갈 세금 식별 번호 검색|아니요|
|Func_prince_edward_island_drivers_license_number|프린스에드워드아일랜드 Edward 섬 운전 면허 번호 검색|아니요|
|Func_quebec_drivers_license_number |퀘벡 운전 면허 번호 검색|아니요|
|Func_randomized_formatted_ssn  |서식이 지정 된 임의 \ 미국 SSN 검색|예|
|Func_randomized_unformatted_ssn|서식이 없는 임의 US SSN 검색|예|
|Func_rhode_island_drivers_license_number|Rhode 섬 운전 면허 번호 검색|아니요|
|Func_romania_eu_national_id_card   |루마니아 p (personal numeric 코드) 검색|아니요|
|Func_saskatchewan_drivers_license_number|서스캐처원 드라이버의 라이선스 번호를 검색 합니다.|아니요|
|Func_slovakia_eu_national_id_card  |슬로바키아 개인 번호 검색|아니요|
|Func_slovenia_eu_national_id_card  |슬로베니아 고유 마스터 시민 번호 검색|아니요|
|Func_slovenia_eu_tax_file_number   |슬로베니아 세금 파일 번호 검색|아니요|
|Func_south_africa_identification_number|남아프리카 식별 번호 검색|예|
|Func_south_carolina_drivers_license_number|남쪽 Carolina 운전 면허 번호 검색|아니요|
|Func_south_dakota_drivers_license_number|남쪽 Dakota 운전 면허 번호 검색|아니요|
|Func_south_korea_resident_number   |대한민국 번호 검색|아니요|
|Func_spain_eu_DL_and_NI_number_citizen |스페인 DL 및 NI 수 시민 감지|아니요|
|Func_spain_eu_DL_and_NI_number_foreigner|스페인 DL 및 NI 번호 foreigner 검색|아니요|
|Func_spain_eu_driver ' s_license_number  |스페인 운전 면허 번호를 감지 합니다.|아니요|
|Func_spain_eu_tax_file_number  |스페인 세금 파일 번호 검색|아니요|
|Func_spanish_social_security_number|스페인어 주민 등록 번호 검색|아니요|
|Func_ssn   |비 임의 서식이 지정 된 US SSN을 검색 하는 함수|예|
|Func_sweden_eu_tax_file_number|스웨덴 세금 파일 번호 검색|아니요|
|Func_swedish_national_identifier|스웨덴어 국가 식별자 검색|예|
|Func_swiss_social_security_number_ahv|AHV (스위스 주민 등록 번호)를 검색 합니다.|아니요|
|Func_taiwanese_national_id |대만어 국가 ID 검색|아니요|
|Func_tennessee_drivers_license_number|Tennessee 운전 면허 번호 검색|아니요|
|Func_texas_drivers_license_number  |텍사스 운전 면허 번호 검색|아니요|
|Func_Thai_Citizen_Id   |태국어 시민 일련번호 검색|아니요|
|Func_Turkish_National_Id|터키어 국가 ID 검색|예|
|Func_uk_drivers_license|영국 운전 면허를 감지 합니다.|아니요|
|Func_uk_eu_tax_file_number|영국 고유 taxpayer 번호 검색|아니요|
|Func_uk_nhs_number |영국 NHS 번호 검색|예|
|Func_uk_nino   |영국 NINO 감지|아니요|
|Func_unformatted_canadian_sin|서식이 없는 캐나다 사인 검색|아니요|
|Func_unformatted_itin  |서식 없는 US ITIN 검색|예|
|Func_unformatted_ssn   |임의로 포맷 되지 않은 미국 SSN 검색|예|
|Func_usa_uk_passport   |미국 및 영국 여권 감지|예|
|Func_utah_drivers_license_number|Utah 운전 면허 번호 검색|아니요|
|Func_vermont_drivers_license_number|Vermont 운전 면허 번호를 감지 합니다.|아니요|
|Func_virginia_drivers_license_number|Virginia 운전 면허 번호 검색|아니요|
|Func_washington_drivers_license_number|인천 운전 면허 번호를 감지 합니다.|아니요|
|Func_west_virginia_drivers_license_number|서 부 Virginia 운전 면허 번호 검색|아니요|
|Func_wisconsin_drivers_license_number  |Wisconsin 운전 면허 번호 검색|아니요|
|Func_wyoming_drivers_license_number    |Wyoming 운전 면허 번호 검색|아니요|


## <a name="func_us_date"></a>Func_us_date

Func_us_date에서는 일반적인 미국 형식에서 날짜를 찾습니다. 일반적인 형식은 "월/일/년", "월-일-년" 및 "월 일 년"입니다. 월의 이름 또는 약어는 대/소문자를 구분 하지 않습니다. 
  
예제:
  
- 2016 년 12 월 2 일
    
- 12 월 2 일 2016
    
- dec 02 2016
    
- 12/2/2016
    
- 12/02/16
    
- 2-2016 년 12 월
    
- 12-2-16
    
허용되는 월 이름:
  
- 영어
    
  - 1 월, 2 월, 3 월, 4 월, 5 월, 01 년 6 월, 년 9 월, 10 월, 년 11 월, 12 월
    
  - 1 월 2 월 3 월 4 일. c a 11 월호-2005 년 12 월.
    
## <a name="func_eu_date"></a>Func_eu_date

Fund_eu_dates에서는 일반 E.U. 날짜를 찾습니다. "일/월/년", "일/월/년" 및 "day month year"와 같은 서식 (및 미국 외부의 위치) 월의 이름 또는 약어는 대/소문자를 구분 하지 않습니다.
  
예제:
  
- 2 월 12 일 2016
    
- 02 년 12 월 2016
    
- 2 월 16 일
    
- 2/12/2016
    
- 02/12/16
    
- 2016 년 12 월 2 일
    
- 2-12-16
    
허용되는 월 이름:
  
- 영어
    
  - 1 월, 2 월, 3 월, 4 월, 5 월, 01 년 6 월, 년 9 월, 10 월, 년 11 월, 12 월
    
  - 1 월 2 월 3 월 4 일. c a 11 월호-2005 년 12 월.
    
- 네덜란드어
    
  - januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December
    
  - jan 1 월 maart 년 9 월 8 일
    
- 프랑스어
    
  - janvier, février, mars, avril, mai, juin juillet, août, septembre, octobre, novembre, décembre
    
  - janv. févr. mars avril mai juin juil août 9 월 일. 수정일. déc.
    
- 독일어
    
  - jänuar, februar, märz, 4 월, mai, juni juli, 8 월, 09, oktober, 11 월, dezember
    
  - 1 월/Jän. März Apr. Mai Juni Juli 8 ~ 9. Okt 11 월.
    
- 이탈리아어
    
  - gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, novembre
    
  - genn febbr mar. 년. magg. giugno luglio ag sett ott. 수정일. home.dic.
    
- 포르투갈어
    
  - janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro
    
  - 1 월의 fev mar abr mai 6 월 30 일 전인 11 월 이전 설정
    
- 스페인어
    
  - enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre
    
  - enero 년 2 월 marzo abr mayo의 6 월 최종. agosto/set. 일. 수정일. home.dic.
    
## <a name="func_eu_date1-deprecated"></a>Func_eu_date1(더 이상 사용되지 않음)

> [!NOTE]
> 이 함수는 이제 위의 함수에 포함 되는 포르투갈어 월 이름을 지원 하기 때문에 더 이상 사용 되지 않습니다  `Func_eu_date` . 
  
이 함수는 포르투갈어에서 일반적으로 사용되는 형식의 날짜를 찾습니다. 이 함수의 형식은  `Func_eu_date` 사용 되는 언어에만 다른 것과 동일 합니다.
  
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
> 이 함수는 이제 위의 함수에 포함 되는 네덜란드어 월 이름만 지원 하기 때문에 더 이상 사용 되지 않습니다  `Func_eu_date` . 
  
이 함수는 네덜란드어에서 일반적으로 사용되는 형식의 날짜를 찾습니다. 이 함수의 형식은  `Func_eu_date` 사용 되는 언어에만 다른 것과 동일 합니다.
  
예제:
  
- 2 mei 2016
    
- 02 mei 2016
    
- 2 mei 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-mei-2016
    
- 2-12-16
    
허용되는 월 이름:
  
- 네덜란드어
    
  - januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December
    
  - 1 월 2 일 maart 2007 년 9 월 8 월 9 시, 08 년 11 월
    
## <a name="func_expiration_date"></a>Func_expiration_date

Func_expiration_date에서는 일반적으로 신용 카드에서 사용 되는 형식으로 되어 있는 날짜를 찾습니다. 이 함수는 "month/year", "month-year", "[month name] year" 및 "[month 약어] year" 형식으로 날짜를 일치 시킵니다. 월의 이름 또는 약어는 대/소문자를 구분 하지 않습니다.
  
예제:
  
- MM/YY - 예를 들어 01/11 또는 1/11
    
- MM/YYYY - 예를 들어 01/2011, 1/2011 등
    
- MM-YY -- 예를 들어 01-22 또는 1-11
    
- MM-YYYY -- 예를 들어 01-2000 또는 1-2000
    
다음 형식은 YY 또는 YYYY를 지원합니다.
  
- Month--1 월-2010 또는 1 월-2010 또는 Jan-10 년 1 월-일 예
    
- Month YYYY -- 예를 들어 'january 2010', 'Jan 2010', 'january 10' 또는 'Jan 10'
    
- MonthYYYY -- 예를 들어 'january2010', 'Jan2010', 'january10' 또는 'Jan10'
    
- Month/YYYY--예를 들어 ' 1 월/2010 ' 또는 ' Jan/2010 ' 또는 ' 1 월/10 '
    
허용되는 월 이름:
  
- 영어
    
  - 1 월, 2 월, 3 월, 4 월, 5 월, 01 년 6 월, 년 9 월, 10 월, 년 11 월, 12 월
    
  - 1 월 2 월 3 월 4 일, 08 년 6 시 9 월 8 일
    
## <a name="func_us_address"></a>Func_us_address

Func_us_address는 미국 시/도 이름 또는 우편 약자를 찾은 다음 유효한 우편 번호를 찾습니다. 우편 번호는 미국 주 이름 또는 약어와 관련된 올바른 우편 번호 중 하나여야 합니다. 미국 주 이름과 우편 번호를 문장 부호나 문자로 구분할 수 없습니다.
  
예제:
  
- Washington 98052
    
- Washington 98052-9998
    
- WA 98052
    
- WA 98052-9998
