---
title: 중요한 정보 유형 엔터티 정의
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: reference
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
hideEdit: true
feedback_system: None
description: 보안 및 준수 센터의 DLP (데이터 손실 방지)에는 &amp; dlp 정책에서 사용할 준비가 된 80 중요 한 정보 유형이 포함 되어 있습니다. 이 항목에서는 이러한 모든 중요한 정보 유형의 목록과 DLP 정책이 이러한 각 유형을 검색할 때 찾는 내용을 보여 줍니다.
ms.openlocfilehash: 71969a58acd64c3e830da398288249cbb8610b5f
ms.sourcegitcommit: 445b249a6f0420b32e49742fd7744006c7090b2b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/18/2020
ms.locfileid: "46797796"
---
# <a name="sensitive-information-type-entity-definitions"></a>중요한 정보 유형 엔터티 정의

준수 센터의 DLP (데이터 손실 방지)에는 DLP 정책에서 사용할 수 있는 중요 한 정보 유형이 많이 포함 되어 있습니다. 이 항목에서는 이러한 모든 중요한 정보 유형의 목록과 DLP 정책이 이러한 각 유형을 검색할 때 찾는 내용을 보여 줍니다. 중요한 정보 유형은 정규식이나 함수로 식별될 수 있는 패턴으로 정의됩니다. 또한 키워드 및 체크섬과 같은 확증적인 증거를 사용하여 중요한 정보 유형을 식별할 수 있습니다. 이러한 평가 프로세스에서 신뢰 수준 및 근접성도 사용됩니다.
  
## <a name="aba-routing-number"></a>ABA 라우팅 번호

### <a name="format"></a>형식일

서식 있는 패턴 또는 서식 없는 패턴으로 표시될 수 있는 9자리 숫자

### <a name="pattern"></a>패턴

서식이
- 0, 1, 2, 3, 6, 7 또는 8로 시작하는 4자리 숫자
- 하이픈
- 4자리 숫자
- 하이픈
- 1자리 숫자

서식 없음: 0, 1, 2, 3, 6, 7 또는 8로 시작 하는 9 개의 연속 숫자 

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Func_aba_routing 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_ABA_Routing의 키워드가 발견되었습니다.

```xml
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a>키워드

#### <a name="keyword_aba_routing"></a>Keyword_ABA_Routing

- aba
- aba #
- aba routing #
- aba routing number
- aba #
- abarouting #
- aba number
- abaroutingnumber
- american bank association routing #
- american bank association routing number
- americanbankassociationrouting #
- americanbankassociationroutingnumber
- bank routing number
- bankrouting #
- bankroutingnumber
- routing transit number
- RTN 
   
## <a name="argentina-national-identity-dni-number"></a>아르헨티나 국가 id (DNI) 번호

### <a name="format"></a>형식일

마침표로 구분된 8자리 숫자

### <a name="pattern"></a>패턴

8자리 숫자:
- 2자리 숫자
- 마침표 
- 3자리 숫자
- 마침표 
- 3자리 숫자

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- 정규식 Regex_argentina_national_id 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keyword_argentina_national_id에서 키워드가 발견 되었습니다.

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_argentina_national_id"></a>Keyword_argentina_national_id

- Argentina National Identity number 
- ID 
- 식별 국가 Id 카드 
- DNI 
- 개인의 NIC 국내 레지스트리 
- Documento Nacional de Identidad 
- Registro Nacional de las Personas 
- Identidad 
- Identificación 
   
## <a name="australia-bank-account-number"></a>오스트레일리아 은행 계좌 번호

### <a name="format"></a>형식일

6-10자리 숫자(은행 지점 번호 포함 또는 제외)

### <a name="pattern"></a>패턴

계좌 번호는 6-10자리 숫자입니다.
호주 은행 지점 번호:
- 3자리 숫자 
- 하이픈 
- 3자리 숫자

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Regex_australia_bank_account_number 정규식이 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_australia_bank_account_number의 키워드가 발견되었습니다.
- Regex_australia_bank_account_number_bsb 정규식이 해당 패턴과 일치하는 콘텐츠를 찾습니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Regex_australia_bank_account_number 정규식이 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_australia_bank_account_number의 키워드가 발견되었습니다.

```xml
<!-- Australia Bank Account Number -->
<Entity id="74a54de9-2a30-4aa0-a8aa-3d9327fc07c7" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
        <Match idRef="Regex_australia_bank_account_number_bsb" />
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
  </Pattern>
 </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_australia_bank_account_number"></a>Keyword_australia_bank_account_number

- swift bank code
- correspondent bank
- base currency
- usa account
- holder address
- bank address
- information account
- fund transfers
- bank charges
- bank details
- banking information
- full names
- iaea

   
## <a name="australia-drivers-license-number"></a>오스트레일리아 운전 면허 번호

### <a name="format"></a>형식일

9개의 문자 및 숫자

### <a name="pattern"></a>패턴

9개의 문자 및 숫자: 

- 2자리 숫자 또는 문자(대/소문자 구분 안 함) 
- 2자리 숫자 
- 5자리 숫자 또는 문자(대/소문자 구분 안 함)

또는

- 1-2개의 선택적 문자(대/소문자 구분 안 함) 
- 4-9자리 숫자

또는

- 9자리 숫자 또는 문자(대/소문자 구분 안 함)

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Regex_australia_drivers_license_number 정규식이 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_australia_drivers_license_number의 키워드가 발견되었습니다.
- Keyword_australia_drivers_license_number_exclusions의 키워드가 발견되지 않았습니다.

```xml
<!-- Australia Drivers License Number -->
<Entity id="1cbbc8f5-9216-4392-9eb5-5ac2298d1356" patternsProximity="300" recommendedConfidence="75">
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_drivers_license_number" />
        <Match idRef="Keyword_australia_drivers_license_number" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_australia_drivers_license_number_exclusions" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_australia_drivers_license_number"></a>Keyword_australia_drivers_license_number

- international driving permits
- australian automobile association
- international driving permit
- DriverLicence
- DriverLicences
- Driver Lic
- Driver Licence
- Driver Licences
- DriversLic
- 드라이버 라이선스
- DriversLicences
- Drivers Lic
- Drivers Lics
- Drivers Licence
- Drivers Licences
- Driver' Lic
- Driver'Lics
- Driver' 라이선스
- Driver'Licences
- Driver'Lic
- Driver' Lics
- Driver' Licence
- Driver'Licences
- Driver'sLic
- Drivers (Slics)
- Driver'sLicence
- Driver'sLicences
- Driver's Lic
- Driver's Lics
- Driver's Licence
- Driver's Licences
- DriverLic #
- DriverLics #
- DriverLicence #
- DriverLicences #
- Driver Lic#
- Driver Lics#
- Driver Licence#
- Driver Licences#
- DriversLic #
- DriversLics #
- 드라이버 라이선스 #
- DriversLicences #
- Drivers Lic#
- Drivers Lics#
- Drivers Licence#
- Drivers Licences#
- Driver' Lic #
- Driver'Lics #
- Driver' 라이선스 #
- Driver'Licences #
- Driver' Lic#
- Driver' Lics#
- Driver' Licence#
- Driver' Licences#
- Driver'sLic #
- Drivers (Slics) #
- Driver'sLicence #
- Driver'sLicences #
- Driver's Lic#
- Driver's Lics#
- Driver's Licence#
- Driver's Licences# 

#### <a name="keyword_australia_drivers_license_number_exclusions"></a>Keyword_australia_drivers_license_number_exclusions

- aaa
- DriverLicense
- DriverLicenses
- Driver License
- Driver Licenses
- 드라이버 라이선스
- 드라이버 라이선스
- Drivers License
- Drivers Licenses
- Driver' 라이선스
- Driver'Licenses
- Driver' License
- Driver' Licenses
- Driver'sLicense
- Driver'sLicenses
- Driver's License
- Driver's Licenses
- DriverLicense #
- DriverLicenses #
- Driver License#
- Driver Licenses#
- 드라이버 라이선스 #
- 드라이버 라이선스 #
- Drivers License#
- Drivers Licenses#
- Driver' 라이선스 #
- Driver'Licenses #
- Driver' License#
- Driver' Licenses#
- Driver'sLicense #
- Driver'sLicenses #
- Driver's License#
- Driver's Licenses#
   
## <a name="australia-medical-account-number"></a>오스트레일리아 의료 계좌 번호

### <a name="format"></a>형식일

10-11자리 숫자

### <a name="pattern"></a>패턴

10-11자리 숫자:
- 첫 번째 숫자는 2-6 범위에 있습니다.
- 9번째 숫자는 검사 숫자입니다.
- 10번째 숫자는 문제 숫자입니다.
- 11번째 숫자(선택 사항)는 개인 번호입니다.

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_australian_medical_account_number 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_Australia_Medical_Account_Number의 키워드가 발견되었습니다.
- 체크섬이 통과됩니다.


```xml
  <!-- Australia Medical Account Number -->
<Entity id="104a99a0-3d3b-4542-a40d-ab0b9e1efe63" recommendedConfidence="85" patternsProximity="300">
    <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_australian_medical_account_number"/>
     <Match idRef="Keyword_Australia_Medical_Account_Number"/>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_australia_medical_account_number"></a>Keyword_Australia_Medical_Account_Number

- bank account details
- medicare payments
- mortgage account
- bank payments
- information branch
- credit card loan
- department of human services
- local service
- medicare

   
## <a name="australia-passport-number"></a>오스트레일리아 여권 번호

### <a name="format"></a>형식일

문자와 7자리 숫자

### <a name="pattern"></a>패턴

1개의 문자(대/소문자 구분 안 함)와 7자리 숫자

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Regex_australia_passport_number 정규식이 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_passport 또는 Keyword_australia_passport_number의 키워드를 찾았습니다.

```xml
<!-- Australia Passport Number -->
<Entity id="29869db6-602d-4853-ab93-3484f905df50" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_passport" />
          <Match idRef="Keyword_australia_passport_number" />
        </Any>
   </Pattern>
</Entity>   
```

### <a name="keywords"></a>키워드

#### <a name="keyword_passport"></a>Keyword_passport

- Passport Number
- Passport No
- Passport #
- 여권 #
- PassportID
- Passportno
- passportnumber
- パスポート
- パスポート番号
- パスポートのNum
- パスポート ＃ 
- Numéro de passeport
- Passeport n °
- Passeport Non
- Passeport #
- 포트 #
- 지/포트 아님
- Passeportn °

#### <a name="keyword_australia_passport_number"></a>Keyword_australia_passport_number

- 여권
- passport details
- immigration and citizenship
- commonwealth of australia
- department of immigration
- residential address
- department of immigration and citizenship
- visa
- national identity card
- passport number
- travel document
- issuing authority
   
## <a name="australia-tax-file-number"></a>오스트레일리아 세금 파일 번호

### <a name="format"></a>형식일

8-9자리 숫자

### <a name="pattern"></a>패턴

일반적으로 다음과 같이 공백과 함께 표시되는 8-9자리 숫자:
- 3자리 숫자 
- 선택적 공백 1개 
- 3자리 숫자 
- 선택적 공백 1개 
- 마지막 숫자가 검사 숫자인 2-3자리 숫자

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_australian_tax_file_number 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_Australia_Tax_File_Number 또는 Keyword_number_exclusions의 키워드가 발견되지 않았습니다.
- 체크섬이 통과됩니다.

```xml
   <!-- Australia Tax File Number -->
    <Entity id="e29bc95f-ff70-4a37-aa01-04d17360a4c5" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_australian_tax_file_number" />
        <Match idRef="Keyword_Australia_Tax_File_Number" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_number_exclusions" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_australia_tax_file_number"></a>Keyword_Australia_Tax_File_Number

- australian business number
- marginal tax rate
- medicare levy
- portfolio number
- service veterans
- withholding tax
- individual tax return
- tax file number
- tfn

#### <a name="keyword_number_exclusions"></a>Keyword_number_exclusions

- 00000000
- 11111111
- 22222222
- 33333333
- 44444444
- 55555555
- 66666666
- 77777777
- 88888888
- 99999999
- 000000000
- 111111111
- 222222222
- 333333333
- 444444444
- 555555555
- 666666666
- 777777777
- 888888888
- 999999999
- 0000000000
- 1111111111
- 2222222222
- 3333333333
- 4444444444
- 5555555555
- 6666666666
- 7777777777
- 8888888888
- 9999999999

## <a name="austria-drivers-license-number"></a>오스트리아 드라이버의 라이선스 번호
이 중요 한 정보 유형 엔터티는 EU 드라이버의 라이선스 번호 중요 정보 유형 에서만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백과 구분 기호가 없는 8 자리 숫자
  
### <a name="pattern"></a>패턴

8자리 숫자
  
### <a name="checksum"></a>제외

아니요
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 정규식이 해당  `Regex_austria_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
- From 키워드를  `Keywords_austria_eu_driver's_license_number` 찾았습니다. 
    
```xml
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>
```

### <a name="keywords"></a>키워드

**Keywords_austria_eu_driver ' s_license_number**
- dl #
- driver license
- 드라이버 라이선스 번호
- 드라이버 라이선스
- drivers lic
- drivers license
- driver's licence
- driver's license
- 운전 면허 번호
- 운전 라이선스 번호
- 운전 면허 번호
- dlno #
- fuhrerschein
- fuhrerschein republik osterreich

## <a name="austria-national-identification-number"></a>오스트리아 국가 식별 번호
이 중요 한 정보 유형 엔터티는 EU 국가 식별 번호 중요 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

문자, 숫자 및 특수 문자의 24 자 조합
  
### <a name="pattern"></a>패턴

24 문자:
  
-  22 개 문자 (대/소문자 구분 안 함), 숫자, 백슬래시, 슬래시 또는 더하기 기호 
    
- 2 개의 문자 (대/소문자 구분 안 함), 숫자, 백슬래시, 슬래시, 더하기 기호 또는 등호
    
### <a name="checksum"></a>제외

해당 사항 없음
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 정규식이 해당  `Regex_austria_eu_national_id_card` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
- From 키워드를  `Keywords_austria_eu_national_id_card` 찾았습니다. 
   
```xml
<!-- EU austria_eu_national_id -->
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_national_id_card" />
          <Match idRef="Keywords_austria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_austria_eu_national_id_card"></a>Keywords_austria_eu_national_id_card

- id 번호
- 
national id
- personalausweis republik österreich

## <a name="austria-passport-number"></a>오스트리아 여권 번호
이 중요 한 정보 유형 엔터티는 EU 여권 번호 sensitiveinformation type 에서만 사용할 수 있습니다.

### <a name="format"></a>형식일

1 개의 문자 다음에 선택적 공백, 일곱 자리 숫자
  
### <a name="pattern"></a>패턴

한 글자, 일곱 자리 및 한 가지 공백 조합입니다.
  
- 1개 문자(대/소문자 구분 안 함)
    
- 1 개의 공백 (선택 사항)
    
- 7자리 숫자
    
### <a name="checksum"></a>제외

해당 사항 없음
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 정규식이 해당  `Regex_austria_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
- From 키워드를  `Keywords_austria_eu_passport_number` 찾았습니다. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

**Keywords_austria_eu_passport_number**
- passport number
- 오스트리아 여권 번호
- passport 아니요
- reisepass
- österreichisch reisepass

## <a name="austria-social-security-number-or-equivalent-identification"></a>오스트리아 주민 등록 번호 또는 동등한 식별
이 중요 한 정보 유형 엔터티는 EU 주민 등록 번호 또는 해당 ID 중요 정보 유형에 서만 사용할 수 있습니다.

### <a name="format"></a>형식일

지정 된 형식의 10 자리 숫자
  
### <a name="pattern"></a>패턴

10자리 숫자:
  
-  일련 번호에 해당 하는 3 자리 숫자 
- 검사 숫자 1 개
- 생년월일에 해당 하는 6 자리 숫자 (DDMMYY)
    
### <a name="checksum"></a>제외

예
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
  
- 이 함수는 해당  `Func_austria_eu_ssn_or_equivalent` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
- From 키워드를  `Keywords_austria_eu_ssn_or_equivalent` 찾았습니다. 
    
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 이 함수는 해당  `Func_austria_eu_ssn_or_equivalent` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_austria_eu_ssn_or_equivalent" />
        </Pattern>
<Pattern confidenceLevel="75">
            <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_austria_eu_ssn_or_equivalent"></a>Keywords_austria_eu_ssn_or_equivalent

- 소셜 보안 아니요
- social security number
- social security code
- 보험 번호
- 오스트리아
- ssn #
- ssn
- 보험 코드
- 보험 코드 #
- 사회 alsecurityno #
- sozialversicherungsnummer
- soziale sicherheit kein
- versicherungsnummer

## <a name="austria-tax-identification-number"></a>오스트리아 세금 식별 번호
이 중요 한 정보 유형 엔터티는 EU 세금 ID 번호 중요 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

하이픈 및 슬래시가 있는 9 자리 숫자
  
### <a name="pattern"></a>패턴

하이픈 및 슬래시가 있는 9 자리 숫자:
  
- 2자리 숫자
- 하이픈 1개(선택 사항)
- 3자리 숫자
- 정방향 슬래시 1개(선택 사항)
- 4자리 숫자
    
### <a name="checksum"></a>제외

예
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
  
- 이 함수는 해당  `Func_austria_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_austria_eu_tax_file_number` 찾았습니다. 
    
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 이 함수는 해당  `Func_austria_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
          <Match idRef="Keywords_austria_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_austria_eu_tax_file_number"></a>Keywords_austria_eu_tax_file_number

- österreich
- st.nr
- steuernummer
- tax id

- 세금 식별 아니요
- 세금 식별 번호
- 세금 없음 #
- 세금 없음
- 세금 번호
- 세금 등록 번호
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- 언급 id
- 언급 아니요
- 언급 #
- 세금 번호

## <a name="azure-documentdb-auth-key"></a>Azure DocumentDB 인증 키

### <a name="format"></a>형식일

아래 패턴에 설명 된 문자 및 문자열이 뒤에 오는 "DocumentDb" 문자열

### <a name="pattern"></a>패턴

- "DocumentDb" 문자열
- 3-200에서 대/소문자, 숫자, 기호, 특수 문자 또는 공백 사이의 조합
- 보다 큼 기호 (>), 등호 (=), 따옴표 (") 또는 아포스트로피 (')
- 86의 대/소문자, 숫자, 슬래시 (/) 또는 더하기 기호 (+)의 조합
- 두 개의 등호 (=)

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- 정규식 CEP_Regex_AzureDocumentDBAuthKey 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- 정규식 CEP_CommonExampleKeywords에서 해당 패턴과 일치 하는 콘텐츠 **를 찾지 않습니다** .

```xml
<!-- Azure Document DB Auth Key -->
<Entity id="0f587d92-eb28-44a9-bd1c-90f2892b47aa" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureDocumentDBAuthKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
          </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

기술적으로이 중요 한 정보 유형은 키워드 목록이 아니라 정규식을 사용 하 여 이러한 키워드를 식별 합니다.

- 극동
- fabrikam
- 대양
- 샌드박스
- 용 onebox
- 로컬
- 127.0.0.1
- testacs입니다.<!--no-hyperlink-->ccw
- s-int<!--no-hyperlink-->투자

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a>Azure IAAS 데이터베이스 연결 문자열 및 Azure SQL 연결 문자열

### <a name="format"></a>형식일

"Server", "server" 또는 "data source" 라는 문자열은 "cloudapp. azure"를 포함 하 여 아래 패턴에 설명 된 문자 및 문자열을 따릅니다.<!--no-hyperlink-->com "또는" cloudapp.<!--no-hyperlink-->net "또는" 데이터베이스.<!--no-hyperlink-->net "과 문자열" Password "또는" password "또는" pwd "가 있습니다.

### <a name="pattern"></a>패턴

- 문자열 "Server", "Server" 또는 "data source"
- 0-2 공백 문자
- 등호 (=)
- 0-2 공백 문자
- 1-200에서 대/소문자, 숫자, 기호, 특수 문자 또는 공백 사이의 조합
- 문자열 "cloudapp.<!--no-hyperlink-->com "," cloudapp.<!--no-hyperlink-->net "또는" database.<!--no-hyperlink-->투자
- 1-300에서 대/소문자, 숫자, 기호, 특수 문자 또는 공백 사이의 조합
- 문자열 "Password", "password" 또는 "pwd"
- 0-2 공백 문자
- 등호 (=)
- 0-2 공백 문자
- 세미콜론 (;), 따옴표 (") 또는 아포스트로피 (')가 아닌 하나 이상의 문자
- 세미콜론 (;), 따옴표 (") 또는 아포스트로피 (')

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- 정규식 CEP_Regex_AzureConnectionString 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- 정규식 CEP_CommonExampleKeywords에서 해당 패턴과 일치 하는 콘텐츠 **를 찾지 않습니다** .

```xml
<!--Azure IAAS Database Connection String and Azure SQL Connection String-->
<Entity id="ce1a126d-186f-4700-8c0c-486157b953fd" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

기술적으로이 중요 한 정보 유형은 키워드 목록이 아니라 정규식을 사용 하 여 이러한 키워드를 식별 합니다.

- 극동
- fabrikam
- 대양
- 샌드박스
- 용 onebox
- 로컬
- 127.0.0.1
- testacs입니다.<!--no-hyperlink-->ccw
- s-int<!--no-hyperlink-->투자

## <a name="azure-iot-connection-string"></a>Azure IoT connection 문자열

### <a name="format"></a>형식일

문자열 "HostName" 뒤에 "azure-devices" 라는 문자열을 포함 하 여 아래 패턴에 설명 된 문자 및 문자열이 표시 됩니다.<!--no-hyperlink-->net "및" SharedAccessKey "

### <a name="pattern"></a>패턴

- 문자열 "HostName"
- 0-2 공백 문자
- 등호 (=)
- 0-2 공백 문자
- 1-200에서 대/소문자, 숫자, 기호, 특수 문자 또는 공백 사이의 조합
- 문자열 "azure-장치<!--no-hyperlink-->투자
- 1-200에서 대/소문자, 숫자, 기호, 특수 문자 또는 공백 사이의 조합
- "SharedAccessKey" 문자열
- 0-2 공백 문자
- 등호 (=)
- 0-2 공백 문자
- 43의 대/소문자, 숫자, 슬래시 (/) 또는 더하기 기호 (+)의 조합
- 등호 (=)

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- 정규식 CEP_Regex_AzureIoTConnectionString 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- 정규식 CEP_CommonExampleKeywords에서 해당 패턴과 일치 하는 콘텐츠 **를 찾지 않습니다** .

```xml
<!--Azure IoT Connection String-->
<Entity id="0b34bec3-d5d6-4974-b7b0-dcdb5c90c29d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureIoTConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

기술적으로이 중요 한 정보 유형은 키워드 목록이 아니라 정규식을 사용 하 여 이러한 키워드를 식별 합니다.

- 극동
- fabrikam
- 대양
- 샌드박스
- 용 onebox
- 로컬
- 127.0.0.1
- testacs입니다.<!--no-hyperlink-->ccw
- s-int<!--no-hyperlink-->투자

## <a name="azure-publish-setting-password"></a>Azure 게시 설정 암호

### <a name="format"></a>형식일

문자열 "userpwd =" 다음에 영숫자 문자열이 나옵니다.

### <a name="pattern"></a>패턴

- 문자열 "userpwd ="
- 60 대 문자와 숫자의 조합
- 큰따옴표 (")

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- 정규식 CEP_Regex_AzurePublishSettingPasswords 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- 정규식 CEP_CommonExampleKeywords에서 해당 패턴과 일치 하는 콘텐츠 **를 찾지 않습니다** .


```xml
<!--Azure Publish Setting Password-->
<Entity id="75f4cc8a-a68e-49e5-89ce-fa8f03d286a5" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
       <IdMatch idRef="CEP_Regex_AzurePublishSettingPasswords" />
       <Any minMatches="0" maxMatches="0">
           <Match idRef="CEP_CommonExampleKeywords" />
       </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

기술적으로이 중요 한 정보 유형은 키워드 목록이 아니라 정규식을 사용 하 여 이러한 키워드를 식별 합니다.

- 극동
- fabrikam
- 대양
- 샌드박스
- 용 onebox
- 로컬
- 127.0.0.1
- testacs입니다.<!--no-hyperlink-->ccw
- s-int<!--no-hyperlink-->투자

## <a name="azure-redis-cache-connection-string"></a>Azure Redis 캐시 연결 문자열

### <a name="format"></a>형식일

문자열 "redis.<!--no-hyperlink-->net "문자열" password "또는" pwd "를 포함 하 여 아래 패턴에 설명 된 문자 및 문자열을 입력 합니다.

### <a name="pattern"></a>패턴

- 문자열 "redis.<!--no-hyperlink-->투자
- 1-200에서 대/소문자, 숫자, 기호, 특수 문자 또는 공백 사이의 조합
- 문자열 "password" 또는 "pwd"
- 0-2 공백 문자
- 등호 (=)
- 0-2 공백 문자
- 대/소문자, 숫자, 슬래시 (/) 또는 더하기 기호 (+)가 있는 43 문자의 조합
- 등호 (=)

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- 정규식 CEP_Regex_AzureRedisCacheConnectionString 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- 정규식 CEP_CommonExampleKeywords에서 해당 패턴과 일치 하는 콘텐츠 **를 찾지 않습니다** .

```xml
<!--Azure Redis Cache Connection String-->
<Entity id="095a7e6c-efd8-46d5-af7b-5298d53a49fc" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureRedisCacheConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

기술적으로이 중요 한 정보 유형은 키워드 목록이 아니라 정규식을 사용 하 여 이러한 키워드를 식별 합니다.

- 극동
- fabrikam
- 대양
- 샌드박스
- 용 onebox
- 로컬
- 127.0.0.1
- testacs입니다.<!--no-hyperlink-->ccw
- s-int<!--no-hyperlink-->투자

## <a name="azure-sas"></a>Azure SAS

### <a name="format"></a>형식일

아래 패턴에 설명 된 문자 및 문자열이 뒤에 오는 문자열 "sig"

### <a name="pattern"></a>패턴

- 문자열 "sig"
- 0-2 공백 문자
- 등호 (=)
- 0-2 공백 문자
- 대/소문자, 숫자 또는 백분율 기호 (%)가 43-53 자 사이의 조합입니다.
- 문자열 "% 3d"
- 소문자 또는 대문자, 숫자 또는 백분율 기호 (%)가 아닌 모든 문자

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- 정규식 CEP_Regex_AzureSAS 해당 패턴과 일치 하는 콘텐츠를 찾습니다.

```xml
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a>Azure Service Bus 연결 문자열

### <a name="format"></a>형식일

문자열 "끝점" 뒤에 "servicebus" 라는 문자열을 포함 하 여 아래 패턴에 나와 있는 문자 및 문자열이 표시 됩니다.<!--no-hyperlink-->net "및" SharedAccesKey "을 차례로 누릅니다.

### <a name="pattern"></a>패턴

- 문자열 "끝점"
- 0-2 공백 문자
- 등호 (=)
- 0-2 공백 문자
- 1-200에서 대/소문자, 숫자, 기호, 특수 문자 또는 공백 사이의 조합
- 문자열 "servicebus.<!--no-hyperlink-->투자
- 1-200에서 대/소문자, 숫자, 기호, 특수 문자 또는 공백 사이의 조합
- "SharedAccessKey" 문자열
- 0-2 공백 문자
- 등호 (=)
- 0-2 공백 문자
- 대/소문자, 숫자, 슬래시 (/) 또는 더하기 기호 (+)가 있는 43 문자의 조합
- 등호 (=)

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- 정규식 CEP_Regex_AzureServiceBusConnectionString 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- 정규식 CEP_CommonExampleKeywords에서 해당 패턴과 일치 하는 콘텐츠 **를 찾지 않습니다** .

```xml
<!--Azure Service Bus Connection String-->
<Entity id="b9a6578f-a83f-4fcd-bf44-2130bae49a6f" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureServiceBusConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

기술적으로이 중요 한 정보 유형은 키워드 목록이 아니라 정규식을 사용 하 여 이러한 키워드를 식별 합니다.

- 극동
- fabrikam
- 대양
- 샌드박스
- 용 onebox
- 로컬
- 127.0.0.1
- testacs입니다.<!--no-hyperlink-->ccw
- s-int<!--no-hyperlink-->투자

## <a name="azure-storage-account-key"></a>Azure 저장소 계정 키

### <a name="format"></a>형식일

"DefaultEndpointsProtocol" 문자열은 "AccountKey" 문자열을 포함 하 여 아래 패턴에 설명 된 문자 및 문자열을 따릅니다.

### <a name="pattern"></a>패턴

- 문자열 "DefaultEndpointsProtocol"
- 0-2 공백 문자
- 등호 (=)
- 0-2 공백 문자
- 1-200에서 대/소문자, 숫자, 기호, 특수 문자 또는 공백 사이의 조합
- 문자열 "AccountKey"
- 0-2 공백 문자
- 등호 (=)
- 0-2 공백 문자
- 대/소문자, 숫자, 슬래시 (/) 또는 더하기 기호 (+)가 있는 86 문자의 조합
- 두 개의 등호 (=)

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- 정규식 CEP_Regex_AzureStorageAccountKey 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- 정규식 CEP_AzureEmulatorStorageAccountFilter에서 해당 패턴과 일치 하는 콘텐츠 **를 찾지 않습니다** .
- 정규식 CEP_CommonExampleKeywords에서 해당 패턴과 일치 하는 콘텐츠 **를 찾지 않습니다** .

```xml
<!--Azure Storage Account Key-->
<Entity id="c7bc98e8-551a-4c35-a92d-d2c8cda714a7" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_AzureEmulatorStorageAccountFilter" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="cep_azureemulatorstorageaccountfilter"></a>CEP_AzureEmulatorStorageAccountFilter

기술적으로이 중요 한 정보 유형은 키워드 목록이 아니라 정규식을 사용 하 여 이러한 키워드를 식별 합니다.

- Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw = =

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

기술적으로이 중요 한 정보 유형은 키워드 목록이 아니라 정규식을 사용 하 여 이러한 키워드를 식별 합니다.

- 극동
- fabrikam
- 대양
- 샌드박스
- 용 onebox
- 로컬
- 127.0.0.1
- testacs입니다.<!--no-hyperlink-->ccw
- s-int<!--no-hyperlink-->투자

## <a name="azure-storage-account-key-generic"></a>Azure 저장소 계정 키 (일반)

### <a name="format"></a>형식일

아래 패턴에 윤곽선이 있는 문자 앞 이나 뒤에 오는 86 문자의 대/소문자, 숫자, 슬래시 (/) 또는 더하기 기호 (+)의 조합입니다.

### <a name="pattern"></a>패턴

- 보다 큼 기호 (>), 아포스트로피 ('), 등호 (=), 따옴표 (") 또는 숫자 기호 (#) 0-1
- 대/소문자, 숫자, 슬래시 (/) 또는 더하기 기호 (+)가 있는 86 문자의 조합
- 두 개의 등호 (=)


### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- 정규식 CEP_Regex_AzureStorageAccountKeyGeneric 해당 패턴과 일치 하는 콘텐츠를 찾습니다.

```xml
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```
## <a name="belgium-drivers-license-number"></a>벨기에 운전 면허 번호
이 중요 한 정보 유형 엔터티는 EU 드라이버의 라이선스 번호 중요 정보 유형 에서만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백과 구분 기호가 없는 10 자리 숫자
  
### <a name="pattern"></a>패턴

10자리 숫자
  
### <a name="checksum"></a>제외

아니요
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 정규식이 해당  `Regex_belgium_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_belgium_eu_driver's_license_number` 찾았습니다.
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

**Keywords__belgium_eu_driver ' s_license_number**

- dl #
- driver license
- 드라이버 라이선스 번호
- 드라이버 라이선스
- drivers lic
- drivers license
- drivers licence
- driver's license
- 운전 면허 번호
- 운전 라이선스 번호
- dlno #
- rijbewijs
- rijbewijsnummer
- führerscheinnummer
- fuhrerscheinnummer
- fuehrerscheinnummer
- führerschein-veiligheid
- fuehrerschein-Veiligheid
- fuehrerschein-veiligheid

## <a name="belgium-national-number"></a>벨기에 국가 번호
이 중요 한 정보 유형 엔터티는 EU 국가 식별 번호 중요 한 정보 유형에 포함 되며 독립 실행형 중요 한 정보 유형 엔터티로 사용할 수 있습니다.

### <a name="format"></a>형식일

11자리 숫자와 구분 기호

### <a name="pattern"></a>패턴

11자리 숫자와 구분 기호:
- 생년월일을 나타내는 YY.MM.DD 형식의 6자리 숫자와 마침표 2개  
- 하이픈 
- 세 개의 순차적 숫자(남성의 경우 홀수, 여성의 경우 짝수)  
- 마침표  
- 검사 숫자에 해당하는 두 자리 숫자

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Func_belgium_national_number 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keyword_belgium_national_number에서 키워드가 발견 되었습니다.
- 체크섬이 통과됩니다.

```xml
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_belgium_national_number"></a>Keyword_belgium_national_number

- belasting aantal
- bnn #
- bnn
- carte d'identité
- identifiant 국가
- identifiantnational #
- identificatie
- 확인과
- identifikation
- identifikationsnummer
- identifizierung
- identité
- identiteit
- identiteitskaart
- 식별
- inscription
- 국가 번호
- 국가별 레지스터
- nationalnumber #
- nationalnumber
- m #
- m
- numéro d'assuré
- numéro de registre 국립
- numéro de sécurité

- numéro d'identification
- numéro d'immatriculation
- numéro 국가
- numéronational #
- 개인 id 번호
- personalausweis
- personalidnumber #
- registratie
- 등록
- registrationsnumme
- registrierung
- social security number

- ssn #
- ssn
- steuernummer
- tax id

- 세금 식별 아니요
- 세금 식별 번호
- 세금 없음 #
- 세금 없음
- 세금 번호
- 세금 등록 번호
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- 언급 id
- 언급 아니요
- 언급 #

## <a name="belgium-passport-number"></a>벨기에 여권 번호
이 중요 한 정보 유형 엔터티는 EU (유럽 여권 번호) 중요 한 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백 또는 구분 기호가 없는 2 개 문자 다음에 6 자리 숫자 사용
  
### <a name="pattern"></a>패턴

2 개 문자 및 6 자리 숫자
  
### <a name="checksum"></a>제외

해당 사항 없음
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 정규식이 해당  `Regex_belgium_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_belgium_eu_passport_number` 찾았습니다.

```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

**Keywords_belgium_eu_passport_number**
- passport number
- 벨기에 여권 번호
- passport 아니요
- 고 대/ort
- paspoortnummer
- reisepass kein
- reisepass

## <a name="belgium-social-security-number-or-equivalent-identification"></a>벨기에 주민 등록 번호 또는 동등한 식별
이 중요 한 정보 유형 엔터티는 EU 주민 등록 번호 또는 해당 ID 중요 정보 유형에 서만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백이 나 구분 기호가 없는 11 자리 숫자
  
### <a name="pattern"></a>패턴

11자리 숫자
  
### <a name="checksum"></a>제외

예
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
  
- 이 함수는 해당  `Func_belgium_eu_ssn_or_equivalent` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_belgium_eu_ssn_or_equivalent` 찾았습니다. 
    
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 이 함수는 해당  `Func_belgium_eu_ssn_or_equivalent` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_belgium_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_belgium_eu_ssn_or_equivalent"></a>Keywords_belgium_eu_ssn_or_equivalent

- 벨기에 국가 번호
- 국가 번호
- social security number
- nationalnumber #
- ssn #
- ssn
- nationalnumber
- bnn #
- bnn
- 개인 id 번호
- personalidnumber #
- numéro 국가
- numéro de sécurité
- numéro d'assuré
- identifiant 국가
- identifiantnational #
- numéronational #

## <a name="belgium-tax-identification-number"></a>벨기에 세금 식별 번호
이 중요 한 정보 유형 엔터티는 EU 세금 Identificaiton 번호 중요 한 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백과 구분 기호를 사용 하지 않고 11 자리 숫자
  
### <a name="pattern"></a>패턴

11자리 숫자:
  
- 2자리 숫자
- "0" 또는 "1"
- 1자리 숫자
- "0" 또는 "1" 또는 "2" 또는 "3" 
- 6자리 숫자
    
### <a name="checksum"></a>제외

해당 사항 없음
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 정규식이 해당  `Regex_belgium_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_belgium_eu_tax_file_number` 찾았습니다. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_belgium_eu_tax_file_number"></a>Keywords_belgium_eu_tax_file_number

- belasting aantal
- bnn #
- bnn
- carte d'identité
- identifiant 국가
- identifiantnational #
- identificatie
- 확인과
- identifikation
- identifikationsnummer
- identifizierung
- identité
- identiteit
- identiteitskaart
- 식별
- inscription
- 국가 번호
- 국가별 레지스터
- nationalnumber #
- nationalnumber
- m #
- m
- numéro d'assuré
- numéro de registre 국립
- numéro de sécurité

- numéro d'identification
- numéro d'immatriculation
- numéro 국가
- numéronational #
- 개인 id 번호
- personalausweis
- personalidnumber #
- registratie
- 등록
- registrationsnumme
- registrierung
- social security number

- ssn #
- ssn
- steuernummer
- tax id

- 세금 식별 아니요
- 세금 식별 번호
- 세금 없음 #
- 세금 없음
- 세금 번호
- 세금 등록 번호
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- 언급 id
- 언급 아니요
- 언급 #


## <a name="brazil-cpf-number"></a>브라질 CPF 번호

### <a name="format"></a>형식일

서식이 있거나 서식이 없을 수 있는 검사 숫자를 포함하는 11자리 숫자

### <a name="pattern"></a>패턴

서식이
- 3자리 숫자
- 마침표 
- 3자리 숫자
- 마침표 
- 3자리 숫자
- 하이픈
- 검사 숫자에 해당하는 2자리 숫자

서식
- 마지막 2자리 숫자가 검사 숫자인 11자리 숫자

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_brazil_cpf 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keyword_brazil_cpf에서 키워드가 발견 되었습니다.
- 체크섬이 통과됩니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Func_brazil_cpf 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- 체크섬이 통과됩니다.

```xml
<!-- Brazil CPF Number -->
<Entity id="78e09124-f2c3-4656-b32a-c1a132cd2711" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cpf"/>
     <Match idRef="Keyword_brazil_cpf"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cpf"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_brazil_cpf"></a>Keyword_brazil_cpf

- CPF
- 확인과
- 등록
- 별
- Cadastro de Pessoas Físicas 
- Imposto 
- Identificação 
- Inscrição 
- 고 eita 
   
## <a name="brazil-legal-entity-number-cnpj"></a>브라질 legal 엔티티 번호 (CNPJ)

### <a name="format"></a>형식일

등록 번호, 지점 번호, 검사 숫자 및 구분 기호를 포함하는 14자리 숫자

### <a name="pattern"></a>패턴
14자리 숫자와 구분 기호:
- 2자리 숫자 
- 마침표  
- 3자리 숫자 
- 마침표  
- 3자리 숫자(처음 8자리 숫자는 등록 번호임)  
- 정방향 슬래시 
- 4자리 지점 번호  
- 하이픈 
- 검사 숫자에 해당하는 2자리 숫자

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_brazil_cnpj 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keyword_brazil_cnpj에서 키워드가 발견 되었습니다.
- 체크섬이 통과됩니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Func_brazil_cnpj 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- 체크섬이 통과됩니다.

```xml
<!-- Brazil Legal Entity Number (CNPJ) -->
<Entity id="9b58b5cd-5e90-4df6-b34f-1ebcc88ceae4" recommendedConfidence="85" patternsProximity="300">
   <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cnpj"/>
     <Match idRef="Keyword_brazil_cnpj"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cnpj"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_brazil_cnpj"></a>Keyword_brazil_cnpj

- CNPJ 
- CNPJ/MF 
- CNPJ-MF 
- National Registry of Legal Entities 
- Taxpayers Registry 
- Legal entity 
- Legal entities 
- Registration Status 
- 비즈니스 
- Company
- CNPJ 
- Cadastro Nacional da Pessoa Jurídica 
- Cadastro Geral de Contribuintes 
- CGC 
- Pessoa jurídica 
- Pessoas jurídicas 
- Situação cadastral 
- Inscrição 
- 포털 
   
## <a name="brazil-national-identification-card-rg"></a>브라질 국립 식별 카드 (RG)

### <a name="format"></a>형식일

Registro Geral (이전 형식): 9 자리 숫자

Registro de Identidade (RIC) (새 형식): 11 자리 숫자

### <a name="pattern"></a>패턴

Registro Geral(이전 형식):
- 2자리 숫자 
- 마침표  
- 3자리 숫자 
- 마침표  
- 3자리 숫자 
- 하이픈 
- 검사 숫자에 해당하는 1자리 숫자

Registro de Identidade (RIC) (새 형식):
- 10자리 숫자 
- 하이픈 
- 검사 숫자에 해당하는 1자리 숫자

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_brazil_rg 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keyword_brazil_rg에서 키워드가 발견 되었습니다.
- 체크섬이 통과됩니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Func_brazil_rg 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- 체크섬이 통과됩니다.

```xml
<!-- Brazil National ID Card (RG) -->
<Entity id="486de900-db70-41b3-a886-abdf25af119c" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_rg"/>
     <Match idRef="Keyword_brazil_rg"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_rg"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_brazil_rg"></a>Keyword_brazil_rg

- Cédula de identidade
- identity card
- national id 
- número de rregistro
- registro de Iidentidade 
- registro geral
- RG(이 키워드는 대/소문자를 구분함) 
- RIC(이 키워드는 대/소문자를 구분하지 않음) 


## <a name="bulgaria-drivers-license-number"></a>불가리아 운전 면허 번호
이 중요 한 정보 유형 엔터티는 EU 드라이버의 라이선스 번호 중요 정보 유형 에서만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백과 구분 기호를 사용 하지 않고 9 자리 숫자
  
### <a name="pattern"></a>패턴

9자리 숫자
  
### <a name="checksum"></a>제외

아니요
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 정규식이 해당  `Regex_bulgaria_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_bulgaria_eu_driver's_license_number` 찾았습니다. 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    
```

### <a name="keywords"></a>키워드

**Keywords_bulgaria_eu_driver ' s_license_number**
- dl #
- driver license
- 드라이버 라이선스 번호
- 드라이버 라이선스
- drivers lic
- drivers license
- drivers licence
- driver's license
- 운전 면허 번호
- 운전 라이선스 번호
- 운전 면허 번호
- dlno #
- свидетелство за управление на мпс
- свидетелство за управление на моторно превозно средство
- сумпс
- шофьорска книжка

## <a name="bulgaria-national-identification-number"></a>불가리아 국가 식별 번호
이 중요 한 정보 유형 엔터티는 EU 국가 식별 번호 중요 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백과 구분 기호가 없는 10 자리 숫자
  
### <a name="pattern"></a>패턴

공백과 구분 기호가 없는 10 자리 숫자
  
- 생년월일에 해당 하는 6 자리 숫자 (YYMMDD) 
- 출생 순서에 해당 하는 2 자리 숫자
- 성별에 해당 하는 1 자리 숫자와이에 해당 하는 짝수 자리 숫자 및 암의 홀수 숫자입니다.
- 검사 숫자 1 개

### <a name="checksum"></a>제외

예
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
  
- 이 함수는 해당  `Func_bulgaria_eu_national_id_card` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_bulgaria_national_number` 찾았습니다. 

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 이 함수는 해당  `Func_bulgaria_eu_national_id_card` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
```xml
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
          <Match idRef="Keywords_bulgaria_national_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_bulgaria_national_number"></a>Keywords_bulgaria_national_number

- bnn #
- bnn
- 고 대 cn #
- 고 대 cn
- edinen grazhdanski nomer
- egn #
- egn
- identification number

- 
national id
- 국가 번호
- nationalnumber #
- nationalnumber
- 개인 id
- personal no
- 개인 번호
- personalidnumber #
- social security number

- ssn #
- ssn
- 일정 한 민사 일련번호
- 일관적인 민사
- 일관적인 민사 번호
- uniformcivilno #
- uniformcivilno
- uniformcivilnumber #
- uniformcivilnumber
- 고유한 참여 번호
- егн #
- егн
- единен граждански номер
- идентификационен номер
- личен номер
- лична идентификация
- лично не
- национален номер
- номер на гражданството
- униформ id
- униформ граждански id
- униформ граждански не
- униформ граждански номер
- униформгражданскиid #
- униформгражданскине. #

## <a name="bulgaria-passport-number"></a>불가리아 여권 번호
이 중요 한 정보 유형 엔터티는 EU (유럽 여권 번호) 중요 한 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백과 구분 기호를 사용 하지 않고 9 자리 숫자
  
### <a name="pattern"></a>패턴

 9자리 숫자 
  
### <a name="checksum"></a>제외

아니요
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 정규식이 해당  `Regex_bulgaria_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_bulgaria_eu_passport_number` 찾았습니다. 

```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```
### <a name="keywords"></a>키워드

**Keywords_bulgaria_eu_passport_number**
- passport number
- 불가리아어 여권 번호
- passport 아니요
- номер на паспорта

## <a name="bulgaria-tax-identification-number"></a>불가리아 세금 식별 번호
이 중요 한 정보 유형 엔터티는 EU 세금 식별 번호로 중요 한 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백과 구분 기호가 없는 10 자리 숫자
  
### <a name="pattern"></a>패턴

10자리 숫자
  
### <a name="checksum"></a>제외

예
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
  
- 이 함수는 해당  `Func_bulgaria_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_bulgaria_eu_tax_file_number` 찾았습니다. 

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 이 함수는 해당  `Func_bulgaria_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 

```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
          <Match idRef="Keywords_bulgaria_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_bulgaria_eu_tax_file_number"></a>Keywords_bulgaria_eu_tax_file_number
- bnn #
- bnn
- 고 대 cn #
- 고 대 cn
- edinen grazhdanski nomer
- egn #
- egn
- identification number

- 
national id
- 국가 번호
- nationalnumber #
- nationalnumber
- 개인 id
- personal no
- 개인 번호
- personalidnumber #
- social security number

- ssn #
- ssn
- 일정 한 민사 일련번호
- 일관적인 민사
- 일관적인 민사 번호
- uniformcivilno #
- uniformcivilno
- uniformcivilnumber #
- uniformcivilnumber
- 고유한 참여 번호
- егн #
- егн
- единен граждански номер
- идентификационен номер
- личен номер
- лична идентификация
- лично не
- национален номер
- номер на гражданството
- униформ id
- униформ граждански id
- униформ граждански не
- униформ граждански номер
- униформгражданскиid #
- униформгражданскине. #


## <a name="canada-bank-account-number"></a>캐나다 은행 계좌 번호

### <a name="format"></a>형식일

7 또는 12자리 숫자

### <a name="pattern"></a>패턴

캐나다 은행 계좌 번호는 7 또는 12자리 숫자입니다.

캐나다 은행 계좌 송금 번호:
- 5자리 숫자 
- 하이픈 
- 3 자리 숫자 또는
- "0" 
- 8자리 숫자

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Regex_canada_bank_account_number 정규식이 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_canada_bank_account_number의 키워드가 발견되었습니다.
- Regex_canada_bank_account_transit_number 정규식이 해당 패턴과 일치하는 콘텐츠를 찾습니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Regex_canada_bank_account_number 정규식이 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_canada_bank_account_number의 키워드가 발견되었습니다.

```xml
<!-- Canada Bank Account Number -->
<Entity id="552e814c-cb50-4d94-bbaa-bb1d1ffb34de" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
        <Match idRef="Regex_canada_bank_account_transit_number" />
   </Pattern>
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
   </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_canada_bank_account_number"></a>Keyword_canada_bank_account_number

- canada savings bonds
- canada revenue agency
- canadian financial institution
- direct deposit form
- canadian citizen
- legal representative
- notary public
- commissioner for oaths
- child care benefit
- universal child care
- canada child tax benefit
- income tax benefit
- harmonized sales tax
- social insurance number
- income tax refund
- child tax benefit
- territorial payments
- institution number
- deposit request
- banking information
- direct deposit
   
## <a name="canada-drivers-license-number"></a>캐나다 운전 면허 번호

### <a name="format"></a>형식일

지역마다 다름

### <a name="pattern"></a>패턴

앨버타, 브리티시 콜롬비아, 매니토바, 뉴브런즈윅, 뉴펀들랜드/래브라도, 노바스코샤, 온타리오, 프린스에드워드아일랜드, 퀘벡 및 서스캐처원을 포함하는 다양한 패턴

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Func_[province_name]_drivers_license_number 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_[province_name]_drivers_license_name의 키워드가 발견되었습니다.
- Keyword_canada_drivers_license의 키워드가 발견되었습니다.

```xml
<!-- Canada Driver's License Number -->
    <Entity id="37186abb-8e48-4800-ad3c-e3d1610b3db0" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_alberta_drivers_license_number" />
        <Match idRef="Keyword_alberta_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_british_columbia_drivers_license_number" />
        <Match idRef="Keyword_british_columbia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_manitoba_drivers_license_number" />
        <Match idRef="Keyword_manitoba_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_brunswick_drivers_license_number" />
        <Match idRef="Keyword_new_brunswick_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_newfoundland_labrador_drivers_license_number" />
        <Match idRef="Keyword_newfoundland_labrador_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_nova_scotia_drivers_license_number" />
        <Match idRef="Keyword_nova_scotia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_ontario_drivers_license_number" />
        <Match idRef="Keyword_ontario_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_prince_edward_island_drivers_license_number" />
        <Match idRef="Keyword_prince_edward_island_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_quebec_drivers_license_number" />
        <Match idRef="Keyword_quebec_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_saskatchewan_drivers_license_number" />
        <Match idRef="Keyword_saskatchewan_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_province_name_drivers_license_name"></a>Keyword_ [province_name] _drivers_license_name

- 시/도 약어(예: AB)
- 시/도 이름(예: 앨버타)

#### <a name="keyword_canada_drivers_license"></a>Keyword_canada_drivers_license

- DL
- 된다
- CDL
- CDLS
- DriverLic
- DriverLics
- DriverLicense
- DriverLicenses
- DriverLicence
- DriverLicences
- Driver Lic
- Driver Lics
- Driver License
- Driver Licenses
- Driver Licence
- Driver Licences
- DriversLic
- DriversLics
- 드라이버 라이선스
- DriversLicences
- 드라이버 라이선스
- 드라이버 라이선스
- Drivers Lic
- Drivers Lics
- Drivers License
- Drivers Licenses
- Drivers Licence
- Drivers Licences
- Driver' Lic
- Driver'Lics
- Driver' 라이선스
- Driver'Licenses
- Driver' 라이선스
- Driver'Licences
- Driver'Lic
- Driver' Lics
- Driver' License
- Driver'Licenses
- Driver'Licence
- Driver'Licences
- Driver'sLic
- Drivers (Slics)
- Driver'sLicense
- Driver'sLicenses
- Driver'sLicence
- Driver'sLicences
- Driver's Lic
- Driver's Lics
- Driver's License
- Driver's Licenses
- Driver's Licence
- Driver's Licences
- Permis de Conduire
- id
- 번호가
- idcard number
- idcard numbers
- idcard #
- idcard #s
- idcard card
- idcard cards
- idcard
- identification number
- identification numbers
- identification #
- identification #s
- identification card
- identification cards
- 확인과 
- DL #
- 된다 # 
- CDL # 
- CDLS # 
- DriverLic # 
- DriverLics # 
- DriverLicense # 
- DriverLicenses # 
- DriverLicence # 
- DriverLicences # 
- Driver Lic#
- Driver Lics# 
- Driver License# 
- Driver Licenses# 
- Driver License# 
- Driver Licences# 
- DriversLic # 
- DriversLics # 
- 드라이버 라이선스 # 
- 드라이버 라이선스 # 
- 드라이버 라이선스 # 
- DriversLicences # 
- Drivers Lic# 
- Drivers Lics# 
- Drivers License# 
- Drivers Licenses# 
- Drivers Licence# 
- Drivers Licences# 
- Driver' Lic # 
- Driver'Lics # 
- Driver' 라이선스 # 
- Driver'Licenses # 
- Driver' 라이선스 # 
- Driver'Licences # 
- Driver' Lic# 
- Driver' Lics# 
- Driver' License# 
- Driver' Licenses# 
- Driver' Licence# 
- Driver' Licences# 
- Driver'sLic # 
- Drivers (Slics) # 
- Driver'sLicense # 
- Driver'sLicenses # 
- Driver'sLicence # 
- Driver'sLicences # 
- Driver's Lic# 
- Driver's Lics# 
- Driver's License# 
- Driver's Licenses# 
- Driver's Licence# 
- Driver's Licences# 
- Permis de Conduire# 
- i # 
- 번호가 # 
- idcard card# 
- idcard cards# 
- idcard # 
- identification card# 
- identification cards# 
- 확인과 # 
   
## <a name="canada-health-service-number"></a>캐나다 건강 서비스 번호

### <a name="format"></a>형식일

10자리 숫자

### <a name="pattern"></a>패턴

10자리 숫자

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Regex_canada_health_service_number 정규식이 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_canada_health_service_number의 키워드가 발견되었습니다.

```xml
<!-- Canada Health Service Number -->
<Entity id="59c0bf39-7fab-482c-af25-00faa4384c94" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_health_service_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_health_service_number" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_canada_health_service_number"></a>Keyword_canada_health_service_number

- personal health number
- patient information
- health services
- speciality services
- automobile accident
- patient hospital
- psychiatrist
- workers compensation
- 종류
      
## <a name="canada-passport-number"></a>캐나다 여권 번호

### <a name="format"></a>형식일

2개의 대문자와 6자리 숫자

### <a name="pattern"></a>패턴

2개의 대문자와 6자리 숫자

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Regex_canada_passport_number 정규식이 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_canada_passport_number 또는 Keyword_passport의 키워드를 찾았습니다.

```xml 
<!-- Canada Passport Number -->
<Entity id="14d0db8b-498a-43ed-9fca-f6097ae687eb" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_passport_number" />
          <Match idRef="Keyword_passport" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_canada_passport_number"></a>Keyword_canada_passport_number

- canadian citizenship
- canadian passport
- passport application
- passport photos
- certified translator
- canadian citizens
- processing times
- renewal application

#### <a name="keyword_passport"></a>Keyword_passport

- Passport Number
- Passport No
- Passport #
- 여권 #
- PassportID
- Passportno
- passportnumber
- パスポート
- パスポート番号
- パスポートのNum
- パスポート＃
- Numéro de passeport
- Passeport n °
- Passeport Non
- Passeport #
- 포트 #
- 지/포트 아님
- Passeportn °
   
## <a name="canada-personal-health-identification-number-phin"></a>캐나다 PHIN (개인 건강 식별 번호)

### <a name="format"></a>형식일

9자리 숫자

### <a name="pattern"></a>패턴

9자리 숫자

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 300 Regex_canada_phin 문자 근사에서 해당 패턴과 일치 하는 콘텐츠를 찾는 경우이 유형의 중요 한 정보를 검색 한다는 것을 75% 확신 합니다.
Keyword_canada_phin 또는 Keyword_canada_provinces에서 키워드가 두 개 이상 있습니다.

```xml
<!-- Canada PHIN -->
<Entity id="722e12ac-c89a-4ec8-a1b7-fea3469f89db" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_phin" />
        <Any minMatches="2">
          <Match idRef="Keyword_canada_phin" />
          <Match idRef="Keyword_canada_provinces" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_canada_phin"></a>Keyword_canada_phin

- social insurance number
- health information act
- income tax information
- manitoba health
- health registration
- prescription purchases
- benefit eligibility
- personal health
- power of attorney
- registration number
- personal health number
- practitioner referral
- wellness professional
- patient referral
- health and wellness

#### <a name="keyword_canada_provinces"></a>Keyword_canada_provinces

- Nunavut
- 퀘벡
- Northwest Territories
- 온타리오
- British Columbia
- 앨버타
- 서스캐처원
- 매니토바
- Yukon
- Newfoundland and Labrador
- New Brunswick
- Nova Scotia
- Prince Edward Island
- 캐나다
   
## <a name="canada-social-insurance-number"></a>캐나다 사회 보험 번호

### <a name="format"></a>형식일

선택적 하이픈 또는 공백을 포함하는 9자리 숫자

### <a name="pattern"></a>패턴

서식이
- 3자리 숫자 
- 하이픈 또는 공백 
- 3자리 숫자 
- 하이픈 또는 공백 
- 3자리 숫자

서식 없음: 9 자리 숫자

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_canadian_sin 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- 2개 이상의 다음 항목 조합:
    - Keyword_sin의 키워드가 발견되었습니다.
    - Keyword_sin_collaborative의 키워드가 발견되었습니다.
    - Func_eu_date 함수가 올바른 날짜 형식의 날짜를 찾습니다.
- 체크섬이 통과됩니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Func_unformatted_canadian_sin 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_sin의 키워드가 발견되었습니다.
- 체크섬이 통과됩니다.

```xml
<!-- Canada Social Insurance Number -->
<Entity id="a2f29c85-ecb8-4514-a610-364790c0773e" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_canadian_sin" />
        <Any minMatches="2">
          <Match idRef="Keyword_sin" />
          <Match idRef="Keyword_sin_collaborative" />
          <Match idRef="Func_eu_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_canadian_sin" />
        <Match idRef="Keyword_sin" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_sin"></a>Keyword_sin

- sin 
- social insurance 
- numero d'assurance sociale 
- 죄 
- ssn 
- 있는 ssn 
- social security 
- numero d'assurance social 
- national identification number 
- national id 
- sin # 
- soc ins 
- social ins 

#### <a name="keyword_sin_collaborative"></a>Keyword_sin_collaborative

- driver's license 
- drivers license 
- driver's licence 
- drivers licence 
- DOB 
- 생년월일 
- 생일 
- Date of Birth 
   
## <a name="chile-identity-card-number"></a>칠레 id 카드 번호

### <a name="format"></a>형식일

7-8 자리 숫자와 구분 기호 확인 숫자 또는 문자

### <a name="pattern"></a>패턴

7-8자리 숫자와 구분 기호:
- 1-2자리 숫자 
- 마침표  
- 3자리 숫자 
- 마침표  
- 3자리 숫자 
- 대시 1개 
- 검사 숫자에 해당하는 1자리 숫자 또는 문자(대/소문자 구분 안 함)

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_chile_id_card 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keyword_chile_id_card에서 키워드가 발견 되었습니다.
- 체크섬이 통과됩니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Func_chile_id_card 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- 체크섬이 통과됩니다.

```xml
<!-- Chile Identity Card Number -->
<Entity id="4e979794-49a0-407e-a0b9-2c536937b925" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_chile_id_card"/>
     <Match idRef="Keyword_chile_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_chile_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_chile_id_card"></a>Keyword_chile_id_card

- National Identification Number 
- Identity card 
- ID 
- 확인과 
- Rol Único Nacional 
- 실행 
- Rol Único Tributario 
- RUT 
- Cédula de Identidad 
- Número De Identificación Nacional 
- Tarjeta de identificación 
- Identificación 
   
## <a name="china-resident-identity-card-prc-number"></a>중국의 중국 id 카드 (PRC) 번호

### <a name="format"></a>형식일

18자리 숫자

### <a name="pattern"></a>패턴

18자리 숫자:
- 주소 코드에 해당하는 6자리 숫자  
- 생년월일에 해당하는 YYYYMMDD 형식의 8자리 숫자  
- 주문 코드에 해당하는 3자리 숫자  
- 검사 숫자에 해당하는 1자리 숫자

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_china_resident_id 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keyword_china_resident_id에서 키워드가 발견 되었습니다.
- 체크섬이 통과됩니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Func_china_resident_id 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- 체크섬이 통과됩니다.

```xml
<!-- China Resident Identity Card (PRC) Number -->
<Entity id="c92daa86-2d16-4871-901f-816b3f554fc1" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_china_resident_id"/>
     <Match idRef="Keyword_china_resident_id"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_china_resident_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

### <a name="keyword_china_resident_id"></a>Keyword_china_resident_id

- Resident Identity Card 
- 중국 
- National Identification Card 
- 身份证 
- 居民 身份证 
- 居民身份证 
- 鉴定 
- 身分證 
- 居民 身份證
- 鑑定 
   
## <a name="credit-card-number"></a>신용 카드 번호

### <a name="format"></a>형식일

서식이 있거나 서식이 없을 수 있는 (dddddddddddddddd), Luhn 테스트를 통과 해야 하는 16 자리 숫자입니다.

### <a name="pattern"></a>패턴

Visa, MasterCard, Discover Card, JCB, American Express, 상품권 및 식사권을 비롯하여 전 세계 모든 주요 브랜드 카드를 검색하는 매우 복잡하고 강력한 패턴입니다.

### <a name="checksum"></a>제외

있음(Luhn 체크섬)

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_credit_card 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- 다음 중 하나가 충족됩니다.
    - Keyword_cc_verification의 키워드가 발견되었습니다.
    - Keyword_cc_name의 키워드가 발견되었습니다.
    - Func_expiration_date 함수가 올바른 날짜 형식의 날짜를 찾습니다.
- 체크섬이 통과됩니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 65% 신뢰합니다.
- Func_credit_card 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- 체크섬이 통과됩니다.

```xml
<!-- Credit Card Number -->
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
          <Match idRef="Func_expiration_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_credit_card" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_cc_verification"></a>Keyword_cc_verification

- card verification
- card identification number
- cvn
- cid
- cvc2
- cvv2
- pin block
- security code
- security number
- security no
- issue number
- issue no
- cryptogramme
- numéro de sécurité
- numero de securite
- kreditkartenprüfnummer
- kreditkartenprufnummer
- prüfziffer
- prufziffer
- sicherheits Kode
- sicherheitscode
- sicherheitsnummer
- verfalldatum
- codice di verifica
- cod. sicurezza
- cod sicurezza
- n autorizzazione
- código
- codigo
- cod. seg
- cod seg
- código de segurança
- codigo de seguranca
- codigo de segurança
- código de seguranca
- cód. segurança
- cod. seguranca cod segurança
- cód. seguranca
- cód segurança
- cod seguranca cod segurança
- cód seguranca
- número de verificação
- numero de verificacao
- ablauf
- gültig bis
- gültigkeitsdatum
- gultig bis
- gultigkeitsdatum
- scadenza
- data scad
- fecha de expiracion
- fecha de venc
- vencimiento
- válido hasta
- valido hasta
- vto
- data de expiração
- data de expiracao
- data em que expira
- 유효한 ade
- valor
- vencimento
- Venc 

#### <a name="keyword_cc_name"></a>Keyword_cc_name

- amex
- american express
- americanexpress
- Visa
- mastercard
- master card
- mc 
- mastercards
- master cards
- diner's Club
- diners club
- dinersclub
- discover card
- discovercard
- discover cards
- JCB
- japanese card bureau
- carte blanche
- carteblanche
- credit card
- 참조란 #
- 참조 #:
- expiration date
- exp date
- expiry date
- 날짜 d'expiration
- date d'exp
- date expiration
- bank card
- bankcard
- card number
- card num
- 전화 번호
- 시 번호
- card numbers
- 카드
- credit cards
- creditcards
- ccn
- card holder
- 소유자
- card holders
- 에이 홀더
- check card
- checkcard
- check cards
- checkcards
- debit card
- debitcard
- debit cards
- debitcards
- atm card
- atmcard
- atm cards
- atmcards
- enroute
- en route
- card type
- carte bancaire
- carte de crédit
- carte de credit
- numéro de carte
- numero de carte
- nº de la carte
- nº de carte
- kreditkarte
- karte
- karteninhaber
- karteninhabers
- kreditkarteninhaber
- kreditkarteninstitut
- kreditkartentyp
- eigentümername
- kartennr 
- kartennummer
- kreditkartennummer
- kreditkarten-nummer
- carta di credito
- carta credito
- 카 ta
- n carta
- veiligheid. 카 ta
- nr carta
- numero carta
- numero della carta
- numero di carta
- tarjeta credito
- tarjeta de credito
- tarjeta crédito
- tarjeta de crédito
- tarjeta de atm
- tarjeta atm
- tarjeta debito
- tarjeta de debito
- tarjeta débito
- tarjeta de débito
- nº de tarjeta
- 아니요. de tarjeta
- no de tarjeta
- numero de tarjeta
- número de tarjeta
- tarjeta no
- tarjetahabiente
- cartão de crédito
- cartão de credito
- cartao de crédito
- cartao de credito
- cartão de débito
- cartao de débito
- cartão de debito
- cartao de debito
- débito automático
- debito automatico
- número do cartão
- numero do cartão 
- número do cartao
- numero do cartao
- número de cartão
- numero de cartão
- número de cartao
- numero de cartao
- nº do cartão
- nº do cartao
- n º do cartão
- no do cartão
- no do cartao
- 아니요. do cartão
- 아니요. do cartao 

## <a name="croatia-drivers-license-number"></a>크로아티아 운전 면허 번호
이 중요 한 정보 유형 엔터티는 EU 드라이버의 라이선스 번호 중요 정보 유형 에서만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백과 구분 기호가 없는 8 자리 숫자
  
### <a name="pattern"></a>패턴

8자리 숫자
  
### <a name="checksum"></a>제외

아니요
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 정규식이 해당  `Regex_croatia_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_croatia_eu_driver's_license_number` 찾았습니다. 

```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

**Keywords_croatia_eu_driver ' s_license_number**

- dl #
- driver license
- 드라이버 라이선스 번호
- 드라이버 라이선스
- drivers lic
- drivers license
- drivers licence
- driver's license
- 운전 면허 번호
- 운전 라이선스 번호
- 운전 면허 번호
- dlno #
- vozačka dozvola

## <a name="croatia-identity-card-number"></a>크로아티아 id 카드 번호
이 중요 한 정보 유형 엔터티는 EU 국가 식별 번호 중요 한 정보 유형에 포함 되며 독립 실행형 중요 한 정보 유형 엔터티로 사용할 수 있습니다.


### <a name="format"></a>형식일

9자리 숫자

### <a name="pattern"></a>패턴

9자리 연속 숫자

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Func_croatia_id_card 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keyword_croatia_id_card에서 키워드가 발견 되었습니다.

```xml
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_croatia_id_card"></a>Keyword_croatia_id_card

- majstorski broj građana
- 마스터 시민 번호
- nacidentifikacijski alni broj
- 국가 식별 번호
- oib #
- oib
- osobna iskaznica
- osobni id
- osobni identifikacijski broj
- 개인 식별 번호
- porezni broj
- porezni identifikacijski broj
- tax id

- 세금 식별 아니요
- 세금 식별 번호
- 세금 없음 #
- 세금 없음
- 세금 번호
- 세금 등록 번호
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- 언급 id
- 언급 아니요
- 언급 #

## <a name="croatia-passport-number"></a>크로아티아 여권 번호
이 중요 한 정보 유형 엔터티는 EU (유럽 여권 번호) 중요 한 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백과 구분 기호를 사용 하지 않고 9 자리 숫자
  
### <a name="pattern"></a>패턴

 9자리 숫자 
  
### <a name="checksum"></a>제외

아니요
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 정규식이 해당  `Regex_croatia_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_croatia_eu_passport_number` 찾았습니다. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```
### <a name="keywords"></a>키워드

**Keywords_croatia_eu_passport_number**

- passport number
- 크로아티아어 여권 번호
- passport 아니요
- broj putovnice

   
## <a name="croatia-personal-identification-oib-number"></a>크로아티아 OIB (개인 식별) 번호

### <a name="format"></a>형식일

11자리 숫자

### <a name="pattern"></a>패턴

11자리 숫자:
- 10자리 숫자 
- 최종 자릿수는 국제 데이터 교환 목적을 위한 검사 숫자 이며, HR는 11 자리 숫자 앞에 추가 됩니다.

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_croatia_oib_number 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keyword_croatia_oib_number에서 키워드가 발견 되었습니다.
- 체크섬이 통과됩니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Func_croatia_oib_number 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- 체크섬이 통과됩니다.

```xml
<!-- Croatia Personal Identification (OIB) Number -->
<Entity id="31983b6d-db95-4eb2-a630-b44bd091968d" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_croatia_oib_number"/>
     <Match idRef="Keyword_croatia_oib_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_oib_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_croatia_oib_number"></a>Keyword_croatia_oib_number

- Personal Identification Number
- Osobni identifikacijski broj 
- OIB 

## <a name="croatia-social-security-number-or-equivalent-identification"></a>크로아티아 주민 등록 번호 또는 해당 하는 id
이 중요 한 정보 유형 엔터티는 EU 주민 등록 번호 또는 해당 ID 중요 정보 유형에 서만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백과 구분 기호를 사용 하지 않고 11 자리 숫자
  
### <a name="pattern"></a>패턴

 11자리 숫자:
  
- 10 자리 숫자
- 검사 숫자 1 개
    
### <a name="checksum"></a>제외

예
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
  
- 이 함수는 해당  `Func_croatia_eu_ssn_or_equivalent` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_croatia_eu_ssn_or_equivalent` 찾았습니다. 
    
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 이 함수는 해당  `Func_croatia_eu_ssn_or_equivalent` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_croatia_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_croatia_eu_ssn_or_equivalent"></a>Keywords_croatia_eu_ssn_or_equivalent

- 개인 식별 번호
- 마스터 시민 번호
- national identification number
- social security number
- nationalnumber #
- ssn #
- ssn
- nationalnumber
- bnn #
- bnn
- 개인 id 번호
- personalidnumber #
- oib
- osobni identifikacijski broj
   
## <a name="croatia-tax-identification-number"></a>크로아티아 세금 식별 번호
이 중요 한 정보 유형 엔터티는 EU 세금 Identificaiton 번호 중요 한 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백이 나 구분 기호가 없는 11 자리 숫자
  
### <a name="pattern"></a>패턴

11자리 숫자:
  
- 임의로 선택한 10 자리 숫자
- 검사 숫자 1 개
    
### <a name="checksum"></a>제외

예
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
  
- 이 함수는 해당  `Func_croatia_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_croatia_eu_tax_file_number` 찾았습니다. 
    
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 이 함수는 해당  `Func_croatia_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
          <Match idRef="Keywords_croatia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_croatia_eu_tax_file_number"></a>Keywords_croatia_eu_tax_file_number

- majstorski broj građana
- 마스터 시민 번호
- nacidentifikacijski alni broj
- 국가 식별 번호
- oib #
- oib
- osobna iskaznica
- osobni id
- osobni identifikacijski broj
- 개인 식별 번호
- porezni broj
- porezni identifikacijski broj
- tax id

- 세금 식별 아니요
- 세금 식별 번호
- 세금 없음 #
- 세금 없음
- 세금 번호
- 세금 등록 번호
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- 언급 id
- 언급 아니요
- 언급 #

## <a name="cyprus-drivers-license-number"></a>키프로스 드라이버 라이선스 번호
이 중요 한 정보 유형 엔터티는 EU 드라이버의 라이선스 번호 중요 정보 유형 에서만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백과 구분 기호를 사용 하지 않고 12 자리 숫자
  
### <a name="pattern"></a>패턴

12자리 숫자
  
### <a name="checksum"></a>제외

아니요
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 정규식이 해당  `Regex_cyprus_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_cyprus_eu_driver's_license_number` 찾았습니다.

```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

**Keywords_cyprus_eu_driver ' s_license_number**

- dl #
- driver license
- 드라이버 라이선스 번호
- 드라이버 라이선스
- drivers lic
- drivers license
- drivers licence
- 운전 면허 번호
- 운전 라이선스 번호
- 운전 면허 번호
- dlno #
- άδεια οδήγησης

## <a name="cyprus-national-identification-number"></a>키프로스 국가 식별 번호
이 중요 한 정보 유형 엔터티는 EU 국가 식별 번호 중요 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백과 구분 기호가 없는 10 자리 숫자
  
### <a name="pattern"></a>패턴

 10 자리 숫자 
  
### <a name="checksum"></a>제외

해당 사항 없음
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 정규식이 해당  `Regex_cyprus_eu_national_id_card` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_cyprus_eu_national_id_card` 찾았습니다. 
    
```xml 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_national_id_card" />
          <Match idRef="Keywords_cyprus_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_cyprus_eu_national_id_card"></a>Keywords_cyprus_eu_national_id_card

- id 카드 번호
- id 카드 번호
- kimlik karti
- 국가 식별 번호
- 개인 id 번호
- ταυτοτητασ

## <a name="cyprus-passport-number"></a>키프로스 여권 번호
이 중요 한 정보 유형 엔터티는 EU (유럽 여권 번호) 중요 한 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백 또는 구분 기호가 없는 1 개 문자 다음에 6-8 자리 숫자
  
### <a name="pattern"></a>패턴

한 문자 다음에 6 ~ 8 자리 숫자
  
### <a name="checksum"></a>제외

아니요
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 정규식이 해당  `Regex_cyprus_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.
- From 키워드를  `Keywords_cyprus_eu_passport_number` 찾았습니다. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

**Keywords_cyprus_eu_passport_number**

- passport number
- 키프로스 여권 번호
- passport 아니요
- αριθμό διαβατηρίου

## <a name="cyprus-tax-identification-number"></a>키프로스 세금 식별 번호
이 중요 한 정보 유형 엔터티는 EU 세금 식별 번호로 중요 한 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

지정 된 패턴에서 8 자리 및 1 개 문자
  
### <a name="pattern"></a>패턴

8 자리 숫자와 1 개 문자:
  
-  "0" 
- 7자리 숫자
- 1 개 문자 (대/소문자 구분 안 함)
    
### <a name="checksum"></a>제외

해당 사항 없음
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
  
- 이 함수는 해당  `Func_cyprus_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_cyprus_eu_tax_file_number` 찾았습니다. 
    
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 이 함수는 해당  `Func_cyprus_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
          <Match idRef="Keywords_cyprus_eu_tax_file_number" />
        </Pattern>
Pattern confidenceLevel="75">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_cyprus_eu_tax_file_number"></a>Keywords_cyprus_eu_tax_file_number

- tax id

- 세금 식별 코드
- 세금 식별 아니요
- 세금 식별 번호
- 세금 없음 #
- 세금 없음
- 세금 번호
- 세금 등록 번호
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tic #
- tic
- 언급 id
- 언급 아니요
- 언급 #
- vergi kimlik kodu
- vergi kimlik numarası
- αριθμός φορολογικού μητρώου
- κωδικός φορολογικού μητρώου
- φορολογική ταυτότητα
- φορολογικού κωδικού
- 세금 번호

## <a name="czech-drivers-license-number"></a>체코어 운전 면허 번호
이 중요 한 정보 유형 엔터티는 EU 드라이버의 라이선스 번호 중요 정보 유형 에서만 사용할 수 있습니다.

### <a name="format"></a>형식일

2 개의 문자 다음에 6 자리 숫자
  
### <a name="pattern"></a>패턴

8 개의 문자 및 숫자:
  
- 2 개 문자 (대/소문자 구분 안 함)
- 공백 1개(선택 사항)
- 6자리 숫자

### <a name="checksum"></a>제외

아니요
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 정규식이 해당  `Regex_czech_republic_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_czech_republic_eu_driver's_license_number` 찾았습니다. 

```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a>키워드

**Keywords_czech_republic_eu_driver ' s_license_number**

- dl #
- driver license
- 드라이버 라이선스 번호
- 드라이버 라이선스
- drivers lic
- drivers license
- drivers licence
- driver's license
- 운전 면허 번호
- 운전 면허 번호
- 운전 라이선스 번호
- 운전 면허 번호
- dlno #
- řidičský prúkaz

## <a name="czech-passport-number"></a>체코어 여권 번호
이 중요 한 정보 유형 엔터티는 EU (유럽 여권 번호) 중요 한 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백이 나 구분 기호가 없는 8 자리 숫자
  
### <a name="pattern"></a>패턴

공백이 나 구분 기호가 없는 8 자리 숫자
  
### <a name="checksum"></a>제외

아니요
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 정규식이 해당  `Regex_czech_republic_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_czech_republic_eu_passport_number` 찾았습니다. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

**Keywords_czech_republic_eu_passport_number**

- passport number
- 체코어 여권 번호
- passport 아니요
- cestovní pas
- pas

## <a name="czech-personal-identity-number"></a>체코어 개인 id 번호
이 중요 한 정보 유형 엔터티는 EU 국가 식별 번호 번들에 포함 되며 독립 실행형 중요 한 정보 유형 엔터티로 사용할 수 있습니다.

### <a name="format"></a>형식일

선택적 슬래시 (이전 형식)가 있는 9 자리 숫자와 슬래시 (새 형식)가 있는 10 자리 숫자

### <a name="pattern"></a>패턴

9 자리 숫자 (이전 형식):
- 9자리 숫자

또는

- 출생 날짜를 나타내는 6 자리 숫자
- 정방향 슬래시
- 3자리 숫자

10 자리 숫자 (새 형식):
- 10자리 숫자

또는

- 출생 날짜를 나타내는 6 자리 숫자
- 정방향 슬래시 
- 마지막 숫자가 검사 숫자인 4 자리 숫자

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 300 Func_czech_id_card 문자에 근접 한 경우에는이 유형의 중요 한 정보를 검색 하는 것으로 85% 확신 합니다.
Keyword_czech_id_card에서 키워드가 발견 되었습니다.
체크섬이 통과됩니다.

```xml
<!-- Czech Personal Identity Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497"      patternsProximity="300" recommendedConfidence="85">
   <Pattern confidenceLevel="85">
      <IdMatch idRef="Func_czech_id_card" />
      <Match idRef="Keyword_czech_id_card" />
   </Pattern>
</Entity>
```
### <a name="keywords"></a>키워드

- 체코어 개인 id 번호
- Rodné číslo



## <a name="czech-social-security-number-or-equivalent-identification"></a>체코어 주민 등록 번호 또는 해당 식별
이 중요 한 정보 유형 엔터티는 EU 주민 등록 번호 또는 해당 ID 중요 정보 유형에 서만 사용할 수 있습니다.

### <a name="format"></a>형식일

지정 된 패턴의 10 자리 및 백슬래시
  
### <a name="pattern"></a>패턴

10 자리 숫자와 백슬래시:
  
- 생년월일에 해당 하는 6 자리 숫자 (YYMMDD): 
    
- 백슬래시
    
- 같은 날짜에 태어난 사람을 구분 하는 일련 번호에 해당 하는 3 자리 숫자
    
- 검사 숫자 1 개
    
### <a name="checksum"></a>제외

예
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
  
- 이 함수는 해당  `Func_czech_republic_eu_ssn_or_equivalent` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_czech_republic_eu_ssn_or_equivalent` 찾았습니다. 
    
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 이 함수는 해당  `Func_czech_republic_eu_ssn_or_equivalent` 패턴과 일치 하는 콘텐츠를 찾습니다. 

```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_czech_republic_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_czech_republic_eu_ssn_or_equivalent"></a>Keywords_czech_republic_eu_ssn_or_equivalent

- 돌 번호
- national identification number
- 개인 식별 번호
- social security number
- nationalnumber #
- ssn #
- ssn
- 국가 번호
- 개인 id 번호
- personalidnumber #
- rč
- rodné číslo
- rodne cislo

## <a name="czech-tax-identification-number"></a>체코어 세금 식별 번호
이 중요 한 정보 유형 엔터티는 EU 세금 식별 번호로 중요 한 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

선택적 백슬래시가 있는 9 자리 또는 10 진수
  
### <a name="pattern"></a>패턴

선택적 backslashl이 있는 아홉 자리 숫자
  
- 6자리 숫자 
- 백슬래시 (선택 사항)
- 3 ~ 4 자리 숫자
    
### <a name="checksum"></a>제외

해당 사항 없음
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 정규식이 해당  `Regex_czech_republic_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_czech_republic_eu_tax_file_number` 찾았습니다. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_czech_republic_eu_tax_file_number"></a>Keywords_czech_republic_eu_tax_file_number

- 체코어 공화국 id
- czechidno #
- daňové číslo
- identifikační číslo
- identity no
- id 번호
- identityno #
- identityno
- 보험 번호
- 국가 식별 번호
- 국가 번호
- osobní číslo
- 개인 id 번호
- 개인 번호
- 인 #
- 인
- pojištění číslo
- rodné číslo
- tax id

- 세금 식별 아니요
- 세금 식별 번호
- 세금 없음 #
- 세금 없음
- 세금 번호
- 세금 등록 번호
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- 언급 id
- 언급 아니요
- 언급 #
- 고유 id 번호
- 세금 번호

## <a name="denmark-drivers-license-number"></a>덴마크 운전 면허 번호
이 중요 한 정보 유형 엔터티는 EU 드라이버의 라이선스 번호 중요 정보 유형 에서만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백과 구분 기호가 없는 8 자리 숫자
  
### <a name="pattern"></a>패턴

8자리 숫자
  
### <a name="checksum"></a>제외

예
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 정규식이 해당  `Regex_denmark_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_denmark_eu_driver's_license_number` 찾았습니다. 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

**Keywords_denmark_eu_driver ' s_license_number**

- | dl #
- driver license
- 드라이버 라이선스 번호
- 드라이버 라이선스
- drivers lic
- drivers license
- drivers licence
- driver's license
- 운전 면허 번호
- 운전 라이선스 번호
- 운전 면허 번호
- dlno #
- kørekort
- kørekortnummer


## <a name="denmark-passport-number"></a>덴마크 여권 번호
이 중요 한 정보 유형 엔터티는 EU (유럽 여권 번호) 중요 한 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백과 구분 기호를 사용 하지 않고 9 자리 숫자
  
### <a name="pattern"></a>패턴

 9자리 숫자 
  
### <a name="checksum"></a>제외

아니요
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 정규식이 해당  `Regex_denmark_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_denmark_eu_passport_number` 찾았습니다. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

**Keywords_denmark_eu_passport_number**

- passport number
- 덴마크어 여권 번호
- passport 아니요
- pas
- pasnummer

## <a name="denmark-personal-identification-number"></a>덴마크 개인 식별 번호
이 중요 한 정보 유형 엔터티는 EU 국가 식별 번호 중요 한 정보 유형에 포함 되며 독립 실행형 중요 한 정보 유형 엔터티로 사용할 수 있습니다.

### <a name="format"></a>형식일

하이픈을 포함하는 10자리 숫자

### <a name="pattern"></a>패턴

10자리 숫자:
- 생년월일에 해당하는 DDMMYY 형식의 6자리 숫자  
- 하이픈 
- 마지막 숫자가 검사 숫자인 4자리 숫자

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 300 Regex_denmark_id 문자 근사에서 해당 패턴과 일치 하는 콘텐츠를 찾는 경우이 유형의 중요 한 정보를 검색 한다는 것을 75% 확신 합니다.
Keyword_denmark_id에서 키워드가 발견 되었습니다.
체크섬이 통과됩니다.

```xml
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_denmark_id"></a>Keyword_denmark_id

- centrale personregister
- civilt registreringssystem
- cpr
- cpr #
- gesundheitskarte nummer
- gesundheitsversicherungkarte nummer
- 건강 카드
- 건강 보험 카드 번호
- 건강 보험 번호
- identification number

- identifikationsnummer
- identifikationsnummer #
- id 번호
- krankenkassennummer
- nationalid #
- personalidentityno #
- personnummer
- personnummer #
- reisekrankenversicherungskartenummer
- rejsesygesikringskort
- 번호 (|)
- kode
- nummer에서
- skattenummer
- sundhedsforsikringskort
- sundhedsforsikringsnummer
- sundhed(고 ort)
- sundhedskortnummer
- sygesikring
- sygesikringkortnummer
- 세금 코드
- 여행 의료 보험 카드
- uniqueidentityno #
- 세금 번호
- 세금 등록 번호
- tax id

- 세금 식별 번호
- taxid #
- taxnumber #
- 세금 없음
- taxno #
- taxnumber
- 세금 식별 아니요
- 언급 #
- taxidno #
- taxidnumber #
- 세금 없음 #
- 언급 id
- 언급 아니요

## <a name="denmark-social-security-number-or-equivalent-identification"></a>덴마크 주민 등록 번호 또는 해당 식별
이 중요 한 정보 유형 엔터티는 EU 주민 등록 번호 또는 해당 ID 중요 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

지정 된 패턴의 10 자리 및 하이픈
  
### <a name="pattern"></a>패턴

10 자리 숫자와 하이픈:
  
- 생년월일에 해당 하는 6 자리 숫자 (DDMMYY) 
- 하이픈
- 일련 번호에 해당 하는 4 자리 숫자
    
### <a name="checksum"></a>제외

예
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
  
- 이 함수는 해당  `Func_denmark_eu_ssn_or_equivalent` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_denmark_eu_ssn_or_equivalent` 찾았습니다. 
    
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 이 함수는 해당  `Func_denmark_eu_ssn_or_equivalent` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_denmark_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_denmark_eu_ssn_or_equivalent"></a>Keywords_denmark_eu_ssn_or_equivalent

- 개인 식별 번호
- national identification number
- social security number
- nationalnumber #
- ssn #
- ssn
- 국가 번호
- 개인 id 번호
- personalidnumber #
- cpr-nummer
- personnummer

## <a name="denmark-tax-identification-number"></a>덴마크 세금 식별 번호
이 중요 한 정보 유형 엔터티는 EU 세금 식별 번호로 중요 한 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

하이픈을 포함 하는 10 자리 숫자
  
### <a name="pattern"></a>패턴

Hyphenl를 포함 하는 10 자리 숫자:
  
-  생년월일에 해당 하는 6 자리 숫자 (DDMMYY)
- 하이픈
- 첫 번째 숫자가 출생 세기에 해당 하 고 마지막 숫자가 개별 성별에 해당 하는 시퀀스 번호에 해당 하는 4 자리 숫자 (남성의 경우 홀수 및 암에도 해당)
    
### <a name="checksum"></a>제외

예
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
  
- 이 함수는 해당  `Func_denmark_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_denmark_eu_tax_file_number` 찾았습니다. 
    
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 이 함수는 해당  `Func_denmark_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
          <Match idRef="Keywords_denmark_eu_tax_file_number" />
        </Pattern> 
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_denmark_eu_tax_file_number"></a>Keywords_denmark_eu_tax_file_number

- centrale personregister
- civilt registreringssystem
- cpr
- cpr #
- gesundheitskarte nummer
- gesundheitsversicherungkarte nummer
- 건강 카드
- 건강 보험 카드 번호
- 건강 보험 번호
- identification number

- identifikationsnummer
- identifikationsnummer #
- id 번호
- krankenkassennummer
- nationalid #
- personalidentityno #
- personnummer
- personnummer #
- reisekrankenversicherungskartenummer
- rejsesygesikringskort
- 번호 (|)
- kode
- nummer에서
- skattenummer
- sundhedsforsikringskort
- sundhedsforsikringsnummer
- sundhed(고 ort)
- sundhedskortnummer
- sygesikring
- sygesikringkortnummer
- 세금 코드
- 여행 의료 보험 카드
- uniqueidentityno #
- 세금 번호
- 세금 등록 번호
- tax id

- 세금 식별 번호
- taxid #
- taxnumber #
- 세금 없음
- taxno #
- taxnumber
- 세금 식별 아니요
- 언급 #
- taxidno #
- taxidnumber #
- 세금 없음 #
- 언급 id
- 언급 아니요


## <a name="drug-enforcement-agency-dea-number"></a>DEA (약품 집행 기관) 번호

### <a name="format"></a>형식일

2개 문자와 7자리 숫자

### <a name="pattern"></a>패턴

패턴에는 다음이 모두 포함되어야 합니다.
- 등록 코드에 해당하는 abcdefghjklmnprstux 중 한 문자(대/소문자 구분 안 함) 
- 등록자 성의 첫 문자에 해당하는 한 문자(대/소문자 구분 안 함) 
- 검사 숫자의 마지막 7개 숫자

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_dea_number 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- 체크섬이 통과됩니다.

```xml
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

없음

## <a name="estonia-drivers-license-number"></a>에스토니아 운전 면허 번호
이 중요 한 정보 유형 엔터티는 EU 드라이버의 라이선스 번호 중요 정보 유형 에서만 사용할 수 있습니다.

### <a name="format"></a>형식일

2 개의 문자 다음에 6 자리 숫자
  
### <a name="pattern"></a>패턴

2 개의 문자와 6 자리 숫자:
  
-  문자 "ET" (대/소문자 구분 안 함) 
- 6자리 숫자
    
### <a name="checksum"></a>제외

아니요
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 정규식이 해당  `Regex_estonia_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_estonia_eu_driver's_license_number` 찾았습니다. 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

**Keywords_estonia_eu_driver ' s_license_number**

- dl #
- driver license
- 드라이버 라이선스 번호
- 드라이버 라이선스 번호
- 드라이버 라이선스
- drivers lic
- drivers license
- drivers licence
- driver's license
- 운전 면허 번호
- 운전 면허 번호
- dlno #
- permis de conduire

## <a name="estonia-national-identification-number"></a>에스토니아 국가 식별 번호
이 중요 한 정보 유형 엔터티는 EU 국가 식별 번호 중요 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백과 구분 기호를 사용 하지 않고 11 자리 숫자
  
### <a name="pattern"></a>패턴

11자리 숫자:
  
- 출생의 성별 및 세기에 해당 하는 1 자리 숫자 (예: 1-2 암, 수, 19th 세기, 3-4:20th 세기, 5-6 = 21 세기)
    
- 출생 날짜에 해당 하는 6 자리 숫자 (YYMMDD)
- 같은 날짜에 태어난 사람을 구분 하는 일련 번호에 해당 하는 3 자리 숫자
- 검사 숫자 1 개
    
### <a name="checksum"></a>제외

예
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
  
- 이 함수는 해당  `Func_estonia_eu_national_id_card` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_estonia_eu_national_id_card` 찾았습니다. 
    
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 이 함수는 해당  `Func_estonia_eu_national_id_card` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
```xml
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
          <Match idRef="Keywords_estonia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
</Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_estonia_eu_national_id_card"></a>Keywords_estonia_eu_national_id_card

- id-kaart
- ik
- isikukood #
- isikukood
- maksu id
- maksukohustuslase identifitseerimisnumber
- maksunumber
- 국가 식별 번호
- 국가 번호
- 개인 코드
- 개인 id 번호
- 개인 식별 코드
- 개인 식별 번호
- personalidnumber #
- tax id

- 세금 식별 아니요
- 세금 식별 번호
- 세금 없음 #
- 세금 없음
- 세금 번호
- 세금 등록 번호
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- 언급 id
- 언급 아니요
- 언급 #

## <a name="estonia-passport-number"></a>에스토니아 여권 번호
이 중요 한 정보 유형 엔터티는 EU (유럽 여권 번호) 중요 한 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백 또는 구분 기호가 없는 1 개 문자 다음에 7 자리 숫자
  
### <a name="pattern"></a>패턴

1 개의 문자 다음에 7 자리 숫자
  
### <a name="checksum"></a>제외

아니요
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 정규식이 해당  `Regex_estonia_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_estonia_eu_passport_number` 찾았습니다. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

**Keywords_estonia_eu_passport_number**

- passport number
- 에스토니아어 여권 번호
- passport 아니요
- eesti kodaniku pass

## <a name="estonia-tax-identification-number"></a>에스토니아 세금 식별 번호
이 중요 한 정보 유형 엔터티는 EU 세금 식별 번호로 중요 한 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백이 나 구분 기호가 없는 11 자리 숫자
  
### <a name="pattern"></a>패턴

11자리 숫자:
  
-  성별에 해당 하는 숫자와 홀수로 해당 하 고, 홀수를 지정 하 여 19th 세기에 대해 1, 2를 나타내는 숫자입니다. 3, 20th 세기에 대해 4를 적용 합니다. 21 세기에 대해 5, 6 
    
- 생년월일에 해당 하는 6 자리 숫자 (YYMMDD)
- 같은 날짜에 태어난 사람을 구분 하는 일련 번호에 해당 하는 3 자리 숫자
- 검사 숫자 1 개
    
### <a name="checksum"></a>제외

예
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
  
- 이 함수는 해당  `Func_estonia_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_estonia_eu_tax_file_number` 찾았습니다. 
    
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 이 함수는 해당  `Func_estonia_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
          <Match idRef="Keywords_estonia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_estonia_eu_tax_file_number"></a>Keywords_estonia_eu_tax_file_number

- id-kaart
- ik
- isikukood #
- isikukood
- maksu id
- maksukohustuslase identifitseerimisnumber
- maksunumber
- 국가 식별 번호
- 국가 번호
- 개인 코드
- 개인 id 번호
- 개인 식별 코드
- 개인 식별 번호
- personalidnumber #
- tax id

- 세금 식별 아니요
- 세금 식별 번호
- 세금 없음 #
- 세금 없음
- 세금 번호
- 세금 등록 번호
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- 언급 id
- 언급 아니요
- 언급 #

## <a name="eu-debit-card-number"></a>EU 직불 카드 번호

### <a name="format"></a>형식일

16자리 숫자

### <a name="pattern"></a>패턴

매우 복잡하고 강력한 패턴

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_eu_debit_card 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- 다음 중 하나 이상이 충족됩니다.
    - Keyword_eu_debit_card의 키워드가 발견되었습니다.
    - Keyword_card_terms_dict의 키워드가 발견되었습니다.
    - Keyword_card_security_terms_dict의 키워드가 발견되었습니다.
    - Keyword_card_expiration_terms_dict의 키워드가 발견되었습니다.
    - Func_expiration_date 함수가 올바른 날짜 형식의 날짜를 찾습니다.
- 체크섬이 통과됩니다.

```xml
    <!-- EU Debit Card Number -->
    <Entity id="0e9b3178-9678-47dd-a509-37222ca96b42" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_eu_debit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_eu_debit_card" />
          <Match idRef="Keyword_card_terms_dict" />
          <Match idRef="Keyword_card_security_terms_dict" />
          <Match idRef="Keyword_card_expiration_terms_dict" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_eu_debit_card"></a>Keyword_eu_debit_card

- account number 
- card number 
- card no. 
- security number 
- 참조란 # 

#### <a name="keyword_card_terms_dict"></a>Keyword_card_terms_dict

- acct nbr 
- acct num 
- acct no 
- american express 
- americanexpress 
- americano espresso 
- amex 
- atm card 
- atm cards 
- atm kaart 
- atmcard 
- atmcards 
- atmkaart 
- atmkaarten 
- bancontact 
- bank card 
- bankkaart 
- card holder 
- card holders 
- card num 
- card number 
- card numbers 
- card type 
- cardano numerico 
- 소유자 
- 에이 홀더 
- 전화 번호 
- 시 번호 
- carta bianca 
- carta credito 
- carta di credito 
- cartao de credito 
- cartao de crédito 
- cartao de debito 
- cartao de débito 
- carte bancaire 
- carte blanche 
- carte bleue 
- carte de credit 
- carte de crédit 
- carte di credito 
- carteblanche 
- cartão de credito 
- cartão de crédito 
- cartão de debito 
- cartão de débito 
- cb 
- ccn 
- check card 
- check cards 
- checkcard
- checkcards 
- chequekaart 
- cirrus 
- cirrus-edc-maestro 
- controlekaart 
- controlekaarten 
- credit card 
- credit cards 
- 카드 
- creditcards 
- debetkaart 
- debetkaarten 
- debit card 
- debit cards 
- debitcard 
- debitcards 
- debito automatico 
- diners club 
- dinersclub 
- 찾아보십시오 
- discover card 
- discover cards 
- discovercard 
- discovercards 
- débito automático
- edc 
- eigentümername 
- european debit card 
- hoofdkaart 
- hoofdkaarten 
- in viaggio 
- japanese card bureau 
- japanse kaartdienst 
- jcb 
- kaart 
- kaart num 
- kaartaantal 
- kaartaantallen 
- kaarthouder 
- kaarthouders 
- karte  
- karteninhaber 
- karteninhabers
- kartennr 
- kartennummer 
- kreditkarte 
- kreditkarten-nummer 
- kreditkarteninhaber 
- kreditkarteninstitut 
- kreditkartennummer 
- kreditkartentyp 
- maestro 
- master card 
- master cards 
- mastercard 
- mastercards 
- mc 
- mister cash 
- n carta 
- 카 ta 
- no de tarjeta 
- no do cartao 
- no do cartão 
- 아니요. de tarjeta 
- 아니요. do cartao 
- 아니요. do cartão 
- nr carta 
- veiligheid. 카 ta 
- numeri di scheda 
- numero carta 
- numero de cartao 
- numero de carte 
- numero de cartão 
- numero de tarjeta
- numero della carta 
- numero di carta 
- numero di scheda 
- numero do cartao 
- numero do cartão 
- numéro de carte 
- nº carta 
- nº de carte 
- nº de la carte 
- nº de tarjeta 
- nº do cartao 
- nº do cartão 
- n º do cartão 
- número de cartao 
- número de cartão 
- número de tarjeta 
- número do cartao 
- scheda dell'assegno 
- scheda dell'atmosfera 
- scheda dell'atmosfera 
- scheda della banca 
- scheda di controllo 
- scheda di debito 
- scheda matrice 
- schede dell'atmosfera 
- schede di controllo 
- schede di debito 
- schede matrici 
- scoprono la scheda 
- scoprono le schede 
- 분리 
- supporti di scheda 
- supporto di scheda 
- 스위치 
- tarjeta atm 
- tarjeta credito 
- tarjeta de atm 
- tarjeta de credito 
- tarjeta de debito 
- tarjeta debito 
- tarjeta no
- tarjetahabiente 
- tipo della scheda 
- ufficio giapponese della 
- scheda 
- v pay 
- v-지급 
- visa 
- visa plus 
- visa electron 
- visto 
- visum 
- vpay   

#### <a name="keyword_card_security_terms_dict"></a>Keyword_card_security_terms_dict

- card identification number
- card verification 
- cardi la verifica 
- cid 
- cod seg 
- cod seguranca 
- cod segurança 
- cod sicurezza 
- cod. seg 
- cod. seguranca 
- cod. segurança 
- cod. sicurezza 
- codice di sicurezza 
- codice di verifica 
- codigo 
- codigo de seguranca 
- codigo de segurança 
- crittogramma 
- cryptogram 
- cryptogramme 
- cv2 
- cvc 
- cvc2 
- cvn 
- cvv 
- cvv2 
- cód seguranca 
- cód segurança 
- cód. seguranca 
- cód. segurança 
- código 
- código de seguranca 
- código de segurança 
- de kaart controle 
- geeft nr uit 
- issue no 
- issue number 
- kaartidentificatienummer 
- kreditkartenprufnummer 
- kreditkartenprüfnummer 
- kwestieaantal 
- 아니요. dell'edizione 
- 아니요. di sicurezza 
- numero de securite 
- numero de verificacao 
- numero dell'edizione 
- numero di identificazione della 
- scheda 
- numero di sicurezza 
- numero van veiligheid 
- numéro de sécurité 
- nº autorizzazione 
- número de verificação 
- perno il blocco 
- pin block 
- prufziffer 
- prüfziffer 
- security code 
- security no 
- security number 
- sicherheits kode 
- sicherheitscode 
- sicherheitsnummer 
- speldblok 
- veiligheid 번호: 
- veiligheidsaantal 
- veiligheidscode 
- veiligheidsnummer 
- verfalldatum 

#### <a name="keyword_card_expiration_terms_dict"></a>Keyword_card_expiration_terms_dict

- ablauf 
- data de expiracao 
- data de expiração 
- data del exp 
- data di exp 
- data di scadenza 
- data em que expira 
- data scad 
- data scadenza 
- date de validité 
- datum afloop 
- datum van exp 
- de afloop 
- espira 
- espira 
- exp date 
- exp datum 
- 행사 
- 예정 
- expires 
- 만료 
- fecha de expiracion 
- fecha de venc 
- gultig bis 
- gultigkeitsdatum 
- gültig bis 
- gültigkeitsdatum 
- la scadenza 
- scadenza 
- valable 
- 유효한 ade 
- valido hasta 
- valor 
- venc 
- vencimento 
- vencimiento 
- verloopt 
- vervaldag 
- vervaldatum 
- vto 
- válido hasta 

## <a name="eu-drivers-license-number"></a>EU 운전 면허 번호
EU 드라이버의 라이선스 번호 중요 한 정보 유형에 서 해당 하는 엔터티입니다.

- [오스트리아](#austria-drivers-license-number) 
- [벨기에](#belgium-drivers-license-number)
- [불가리아](#bulgaria-drivers-license-number)
- [크로아티아](#croatia-drivers-license-number)
- [키프로스](#cyprus-drivers-license-number)
- [Czech](#czech-drivers-license-number)
- [덴마크](#denmark-drivers-license-number)
- [에스토니아](#estonia-drivers-license-number)
- [핀란드](#finland-drivers-license-number)
- [프랑스](#france-drivers-license-number) 
- [독일](#germany-drivers-license-number)
- [그리스](#greece-drivers-license-number)
- [헝가리](#hungary-drivers-license-number)
- [아일랜드](#ireland-drivers-license-number)
- [이탈리아](#italy-drivers-license-number)
- [라트비아](#latvia-drivers-license-number)
- [리투아니아](#lithuania-drivers-license-number)
- [셈](#luxemburg-drivers-license-number)
- [몰타](#malta-drivers-license-number)
- [네덜란드](#netherlands-drivers-license-number)
- [폴란드](#poland-drivers-license-number) 
- [포르투갈](#portugal-drivers-license-number)
- [루마니아](#romania-drivers-license-number)
- [슬로바키아](#slovakia-drivers-license-number)
- [슬로베니아](#slovenia-drivers-license-number)
- [스페인](#spain-drivers-license-number)
- [스웨덴](#sweden-drivers-license-number)
- [영국](#uk-drivers-license-number)

## <a name="eu-national-identification-number"></a>EU 국가 식별 번호
EU 국가 식별 번호 중요 한 정보 유형의 엔터티입니다.

- [오스트리아](#austria-national-identification-number)
- [벨기에](#belgium-national-number)
- [불가리아](#bulgaria-national-identification-number)
- [크로아티아](#croatia-identity-card-number)
- [키프로스](#cyprus-national-identification-number)
- [Czech](#czech-personal-identity-number)
- [덴마크](#denmark-personal-identification-number)
- [에스토니아](#estonia-national-identification-number)
- [핀란드](#finland-national-identification-number)
- [프랑스](#france-national-identification-card-cni)
- [독일](#germany-identity-card-number)
- [그리스](#greece-national-id-card)
- [헝가리](#hungary-national-identification-number)
- [아일랜드](#ireland-national-identification-number)
- [이탈리아](#italy-national-identification-number)
- [라트비아](#latvia-national-identification-number)
- [리투아니아](#lithuania-national-identification-number)
- [셈](#luxemburg-national-identification-number)
- [몰타](#malta-national-identification-number)
- [네덜란드](#netherlands-national-identification-number)
- [폴란드](#poland-national-id-pesel)
- [포르투갈](#portugal-citizen-card-number)
- [루마니아](#romania-national-identification-number)
- [슬로바키아](#slovakia-national-identification-number)
- [슬로베니아](#slovenia-national-identification-number)
- [스페인](#spain-national-identification-number)
- [영국](#uk-national-insurance-number-nino)                                        


## <a name="eu-passport-number"></a>EU 여권 번호 
이러한 엔터티는 EU 여권 번호 중요 한 정보 유형으로 서 EU 여권 번호 번들의 엔터티입니다.

- [오스트리아](#austria-passport-number)
- [벨기에](#belgium-passport-number)
- [불가리아](#bulgaria-passport-number)
- [크로아티아](#croatia-passport-number)
- [키프로스](#cyprus-passport-number)
- [Czech](#czech-passport-number)
- [덴마크](#denmark-passport-number)
- [에스토니아](#estonia-passport-number)
- [핀란드](#finland-passport-number)
- [프랑스](#france-passport-number)
- [독일](#germany-passport-number)
- [그리스](#greece-passport-number)
- [헝가리](#hungary-passport-number)
- [아일랜드](#ireland-passport-number)
- [이탈리아](#italy-passport-number)
- [라트비아](#latvia-passport-number)
- [리투아니아](#lithuania-passport-number)
- [셈](#luxemburg-passport-number)
- [몰타](#malta-passport-number)
- [네덜란드](#netherlands-passport-number)
- [폴란드](#poland-passport-number)
- [포르투갈](#portugal-passport-number)
- [루마니아](#romania-passport-number)
- [슬로바키아](#slovakia-passport-number)
- [슬로베니아](#slovenia-passport-number)
- [스페인](#spain-passport-number)
- [스웨덴](#sweden-passport-number)
- [영국](#us--uk-passport-number)


## <a name="eu-social-security-number-or-equivalent-identification"></a>EU 주민 등록 번호 또는 해당 id
이러한 엔터티는 EU 주민 등록 번호 또는 해당 id 중요 정보 유형의 엔터티입니다.

- [오스트리아](#austria-social-security-number-or-equivalent-identification)
- [벨기에](#belgium-social-security-number-or-equivalent-identification)
- [크로아티아](#croatia-social-security-number-or-equivalent-identification)
- [Czech](#czech-social-security-number-or-equivalent-identification)
- [덴마크](#denmark-social-security-number-or-equivalent-identification)
- [핀란드](#finland-social-security-number-or-equivalent-identification)
- [프랑스](#france-social-security-number-insee-or-equivalent-identification)
- [독일](#germany-identity-card-number)
- [그리스](#greece-national-id-card)
- [헝가리](#hungary-social-security-number-or-equivalent-identification)
- [포르투갈](#portugal-citizen-card-number)
- [스페인](#spain-social-security-number-ssn)
- [스웨덴](#sweden-social-security-number-or-equivalent-identification)

## <a name="eu-tax-identification-number"></a>EU 세금 확인 번호

hese 엔터티는 EU 세금 식별 번호 중요 한 정보 유형입니다.

- [오스트리아](#austria-tax-identification-number)
- [벨기에](#belgium-tax-identification-number)
- [불가리아](#bulgaria-tax-identification-number)
- [크로아티아](#croatia-tax-identification-number)
- [키프로스](#cyprus-tax-identification-number)
- [Czech](#czech-tax-identification-number)
- [덴마크](#denmark-tax-identification-number)
- [에스토니아](#estonia-tax-identification-number)
- [핀란드](#finland-tax-identification-number)
- [프랑스](#france-tax-identification-number)
- [독일](#germany-tax-identification-number)
- [그리스](#greece-tax-identification-number)
- [헝가리](#hungary-tax-identification-number)
- [아일랜드](#ireland-tax-identification-number)
- [이탈리아](#italy-tax-identification-number)
- [라트비아](#latvia-tax-identification-number)
- [리투아니아](#lithuania-tax-identification-number)
- [셈](#luxemburg-tax-identification-number)
- [몰타](#malta-tax-identification-number)
- [네덜란드](#netherlands-tax-identification-number)
- [폴란드](#poland-tax-identification-number)
- [포르투갈](#portugal-tax-identification-number)
- [루마니아](#romania-tax-identification-number)
- [슬로바키아](#slovakia-tax-identification-number)
- [슬로베니아](#slovenia-tax-identification-number)
- [스페인](#spain-tax-identification-number)
- [스웨덴](#sweden-tax-identification-number)
- [영국](#uk-tax-identification-number)


## <a name="finland-drivers-license-number"></a>핀란드 운전 면허 번호
이 중요 한 정보 유형 엔터티는 EU 드라이버의 라이선스 번호 중요 정보 유형 에서만 사용할 수 있습니다.

### <a name="format"></a>형식일

하이픈을 포함하는 10자리 숫자
  
### <a name="pattern"></a>패턴

하이픈을 포함 하는 10 자리 숫자:
  
-  6자리 숫자 
- 하이픈
-  4자리 숫자 
    
### <a name="checksum"></a>제외

아니요
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 정규식이 해당  `Regex_finland_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
- From 키워드를  `Keywords_finland_eu_driver's_license_number` 찾았습니다. 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

**Keywords_finland_eu_driver ' s_license_number**

- dl #
- driver license
- 드라이버 라이선스 번호
- 드라이버 라이선스
- drivers lic
- drivers license
- drivers licence
- driver's license
- 운전 면허 번호
- 운전 라이선스 번호
- 운전 면허 번호
- dlno #
- ajokortti

## <a name="finland-national-identification-number"></a>핀란드 국가 식별 번호
이 중요 한 정보 유형 엔터티는 EU 국가 식별 번호 중요 한 정보 유형에 포함 되며 독립 실행형 중요 한 정보 유형 엔터티로 사용할 수 있습니다.

### <a name="format"></a>형식일

세기를 나타내는 6자리 숫자와 문자, 3자리 숫자와 검사 숫자

### <a name="pattern"></a>패턴

패턴에는 다음이 모두 포함되어야 합니다.
- 생년월일에 해당하는 DDMMYY 형식의 6자리 숫자 
- 세기 표시('-', '+' 또는 'a') 
- 3자리 개인 ID 번호 
- 검사 숫자에 해당하는 1자리 숫자 또는 문자(대/소문자 구분 안 함)

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_finnish_national_id 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_finnish_national_id의 키워드가 발견되었습니다.
- 체크섬이 통과됩니다.

```xml
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

- ainutlaatuinen henkilökohtainen tunnus
- henkilökohtainen tunnus
- henkilötunnus
- henkilötunnusnumero #
- henkilötunnusnumero
- hetu
- id 없음
- id 번호
- identification number

- identiteetti numero
- id 번호
- idnumber
- kansallinen henkilötunnus
- kansallisen henkilökortin
- 국가 id 카드
- 국가 id 번호입니다.
- 개인 id
- 개인 id 코드
- personalidnumber #
- personbeteckning
- personnummer
- social security number

- sosiaaliturvatunnus
- tax id

- 세금 식별 아니요
- 세금 식별 번호
- 세금 없음 #
- 세금 없음
- 세금 번호
- 세금 등록 번호
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- 언급 id
- 언급 아니요
- 언급 #
- tunnistenumero
- tunnus numero
- tunnusluku
- tunnusnumero
- verokortti
- veronumero
- verotunniste
- verotunnus

## <a name="finland-passport-number"></a>핀란드 여권 번호
이 중요 한 정보 유형 엔터티는 EU 여권 번호 중요 한 정보 유형으로 제공 되며 독립 실행형 중요 한 정보 유형 엔터티로 사용할 수 있습니다.

### <a name="format"></a>형식일
9개의 문자와 숫자의 조합

### <a name="pattern"></a>패턴
9 개의 문자 및 숫자 조합: 2 개 문자 (대/소문자 구분 안 함) 7 자리 숫자

### <a name="checksum"></a>제외
아니요

### <a name="definition"></a>정의
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- 정규식 Regex_finland_passport_number 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keyword_finland_passport_number에서 키워드가 발견 되었습니다.

```xml
<!-- Finland Passport Number -->
<Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_finland_passport_number"/>
     <Match idRef="Keyword_finland_passport_number"/>
  </Pattern>
</Entity>
```
### <a name="keywords"></a>키워드
- Keyword_finland_passport_number
- 여권
- 에이 si

## <a name="finland-social-security-number-or-equivalent-identification"></a>핀란드 주민 등록 번호 또는 동등한 식별
이 중요 한 정보 유형 엔터티는 EU 주민 등록 번호 또는 해당 ID 중요 정보 유형에 서만 사용할 수 있습니다.

### <a name="format"></a>형식일

지정 된 형식의 11 자 조합
  
### <a name="pattern"></a>패턴

다음은 지정 된 형식의 11 자 조합입니다.
  
-  6자리 숫자 
- 다음 중 하나의 인스턴스에 대해 다음을 수행 합니다.
  - 더하기 기호
  - 빼기 기호
  - 문자 "A" (대/소문자 구분 안 함)
- 3자리 숫자
- 1 개의 문자 또는 1 자리 숫자
    
### <a name="checksum"></a>제외

예
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
  
- 이 함수는 해당  `Func_finland_eu_ssn_or_equivalent` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_finland_eu_ssn_or_equivalent` 찾았습니다. 
    
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 이 함수는 해당  `Func_finland_eu_ssn_or_equivalent` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_finland_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_finland_eu_ssn_or_equivalent"></a>Keywords_finland_eu_ssn_or_equivalent

- identification number
- 개인 id
- id 번호
- 핀란드어 국가 id 번호
- personalidnumber #
- national identification number
- id 번호
- 국가 id 번호입니다.
- 국가 id 번호
- id 없음
- tunnistenumero
- henkilötunnus
- yksilöllinen henkilökohtainen tunnistenumero
- ainutlaatuinen henkilökohtainen tunnus
- identiteetti numero
- suomen kansallinen henkilötunnus
- henkilötunnusnumero #
- kansallisen tunnistenumero
- tunnusnumero
- kansallinen tunnus numero
- hetu

## <a name="finland-tax-identification-number"></a>핀란드 세금 식별 번호
이 중요 한 정보 유형 엔터티는 EU 세금 식별 번호로 중요 한 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

숫자, 문자, 더하기 및 빼기 기호를 11 문자로 조합
  
### <a name="pattern"></a>패턴

숫자, 문자, 더하기 및 빼기 기호를 11 문자로 조합한 것입니다.
  
- 6자리 숫자
- 더하기 기호, 빼기 기호 또는 + 기호가 1800-1899 사이에 태어난 것을 의미 하는 "A" (대/소문자 구분 안 함), 빼기 기호는 1900-1999 사이에 출생를 의미 하며 "A"는 "A"를 2000 의미 합니다.
- 3자리 숫자
- 1 개의 문자 또는 한 자리 숫자
    
### <a name="checksum"></a>제외

예
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
  
- 이 함수는 해당  `Func_finland_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_finland_eu_tax_file_number` 찾았습니다. 
    
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 이 함수는 해당  `Func_finland_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
          <Match idRef="Keywords_finland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_finland_eu_tax_file_number"></a>Keywords_finland_eu_tax_file_number

- ainutlaatuinen henkilökohtainen tunnus
- henkilökohtainen tunnus
- henkilötunnus
- henkilötunnusnumero #
- henkilötunnusnumero
- hetu
- id 없음
- id 번호
- identification number

- identiteetti numero
- id 번호
- idnumber
- kansallinen henkilötunnus
- kansallisen henkilökortin
- 국가 id 카드
- 국가 id 번호입니다.
- 개인 id
- 개인 id 코드
- personalidnumber #
- personbeteckning
- personnummer
- social security number

- sosiaaliturvatunnus
- suomen kansallinen henkilötunnus
- tax id

- 세금 식별 아니요
- 세금 식별 번호
- 세금 없음 #
- 세금 없음
- 세금 번호
- 세금 등록 번호
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- 언급 id
- 언급 아니요
- 언급 #
- tunnistenumero
- tunnus numero
- tunnusluku
- tunnusnumero
- verokortti
- veronumero
- verotunniste
- verotunnus


## <a name="france-drivers-license-number"></a>프랑스 운전 면허 번호
이 중요 한 정보 유형 엔터티는 EU 드라이버의 라이선스 번호 중요 정보 유형에 서 사용할 수 있으며 독립 실행형 중요 한 정보 유형 엔터티로 사용할 수 있습니다.

### <a name="format"></a>형식일

12자리 숫자

### <a name="pattern"></a>패턴

비슷한 패턴(예: 프랑스 전화 번호)을 무시하기 위한 유효성 검사 기능을 포함하는 12자리 숫자

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Func_french_drivers_license 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- 다음 중 하나 이상이 충족됩니다.
- Keyword_french_drivers_license의 키워드가 발견되었습니다.
- Func_eu_date 함수가 올바른 날짜 형식의 날짜를 찾습니다.

```xml
<!-- France Driver's License Number -->
<Entity id="18e55a36-a01b-4b0f-943d-dc10282a1824" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_french_drivers_license" />
        <Any minMatches="1">
          <Match idRef="Keyword_french_drivers_license" />
          <Match idRef="Func_eu_date" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_french_drivers_license"></a>Keyword_french_drivers_license

- drivers licence
- drivers license
- driving licence
- driving license
- permis de conduire
- licence number
- license number
- licence numbers
- license numbers

## <a name="france-national-identification-card-cni"></a>프랑스 국가 식별 카드 (CNI)
이 중요 한 정보 유형 엔터티는 EU 국가 식별 번호 중요 한 정보 유형에 포함 되며 독립 실행형 중요 한 정보 유형 엔터티로 사용할 수 있습니다.

### <a name="format"></a>형식일

12자리 숫자

### <a name="pattern"></a>패턴

12자리 숫자

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 65% 신뢰합니다.
- Regex_france_cni 정규식이 해당 패턴과 일치하는 콘텐츠를 찾습니다.

```xml
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

- card number

- carte nationale d'identité
- carte nationale d'idenite no
- cni #
- cni
- compte bancaire
- 국가 식별 번호
- 국가 id
- nationalidno #
- numéro d'assurance maladie
- numéro de carte vitale

   
## <a name="france-passport-number"></a>프랑스 여권 번호
이 중요 한 정보 유형 엔터티는 EU 여권 번호 중요 한 정보 유형으로 제공 되며 독립 실행형 중요 한 정보 유형 엔터티로 사용할 수 있습니다.

### <a name="format"></a>형식일

9자리 숫자 및 문자

### <a name="pattern"></a>패턴

9자리 숫자 및 문자:
- 2자리 숫자 
- 2문자(대/소문자 구분 안 함) 
- 5자리 숫자

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Func_fr_passport 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_passport의 키워드가 발견되었습니다.

```xml
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_passport"></a>Keyword_passport

- Passport Number
- Passport No
- Passport #
- 여권 #
- PassportID
- Passportno
- passportnumber
- パスポート
- パスポート番号
- パスポートのNum
- パスポート ＃ 
- Numéro de passeport
- Passeport n °
- Passeport Non
- Passeport #
- 포트 #
- 지/포트 아님
- Passeportn °

      
## <a name="france-social-security-number-insee-or-equivalent-identification"></a>프랑스 사회 보장 번호 (INSEE) 또는 동등한 식별
이 중요 한 정보 유형 엔터티는 EU 주민 등록 번호 및 해당 ID와 관련 된 중요 한 정보 유형으로 포함 되며 독립 실행형 중요 한 정보 유형 엔터티로 사용할 수 있습니다.

### <a name="format"></a>형식일

15자리 숫자

### <a name="pattern"></a>패턴

다음 두 패턴 중 하나가 일치해야 합니다.
- 13 자리 숫자와 공백 다음 두 자리 숫자<br/>
또는
- 15자리 연속 숫자

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 95% 신뢰합니다.
- Func_french_insee 또는 Func_fr_insee 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keyword_fr_insee의 키워드가 발견되었습니다.
- 체크섬이 통과됩니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_french_insee 또는 Func_fr_insee 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keyword_fr_insee의 키워드가 발견되지 않았습니다.
- 체크섬이 통과됩니다.

```xml
<!-- France INSEE -->
<Entity id="71f62b97-efe0-4aa1-aa49-e14de253619d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="95">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Func_fr_insee" />
        <Any minMatches="1">
          <Match idRef="Keyword_fr_insee" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Func_fr_insee" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_fr_insee" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_fr_insee"></a>Keyword_fr_insee

- insee
- securité sociale
- securite sociale
- national id
- national identification
- numéro d'identité
- no d'identité
- 아니요. d'identité
- numero d'identite
- no d'identite
- 아니요. d'identite
- social security number
- social security code
- social insurance number
- le numéro d'identification nationale
- d'identité nationale
- numéro de sécurité sociale
- le code de la sécurité sociale
- numéro d'assurance sociale
- numéro de sécu
- code sécu 

## <a name="france-tax-identification-number"></a>프랑스 세금 식별 번호
이 중요 한 정보 유형 엔터티는 EU 세금 식별 번호로 중요 한 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

개별 사용자의 경우 13 자리 숫자 및 엔터티의 경우 9 자리 숫자
  
### <a name="pattern"></a>패턴

개별 사용자에 대 한 13 자리 숫자:
  
- 0, 1, 2 또는 3 이어야 하는 1 자리 숫자
- 12자리 숫자
    
엔터티의 9 자리 숫자
  
### <a name="checksum"></a>제외

해당 사항 없음
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
  
- 이 함수는 해당  `Func_france_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_france_eu_tax_file_number` 찾았습니다. 
    
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 이 함수는 해당  `Func_france_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
          <Match idRef="Keywords_france_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_france_eu_tax_file_number"></a>Keywords_france_eu_tax_file_number

- numéro d'identification fiscale
- tax id

- 세금 식별 아니요
- 세금 식별 번호
- 세금 없음 #
- 세금 없음
- 세금 번호
- 세금 등록 번호
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- 언급 id
- 언급 아니요
- 언급 #

## <a name="germany-drivers-license-number"></a>독일 운전 면허 번호
이 중요 한 정보 유형 엔터티는 EU 드라이버의 라이선스 번호 중요 한 정보 유형에 포함 되며 독립 실행형 중요 한 정보 유형 엔터티로 사용할 수 있습니다.

### <a name="format"></a>형식일

11자리 숫자와 문자 조합

### <a name="pattern"></a>패턴

11자리 숫자와 문자(대/소문자 구분 안 함):
- 1자리 숫자 또는 문자 
- 2자리 숫자 
- 6자리 숫자 또는 문자 
- 1자리 숫자 
- 1자리 숫자 또는 문자

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Func_german_drivers_license 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- 다음 중 하나 이상이 충족됩니다.
    - Keyword_german_drivers_license_number의 키워드가 발견되었습니다.
    - Keyword_german_drivers_license_collaborative의 키워드가 발견되었습니다.
    - Keyword_german_drivers_license의 키워드가 발견되었습니다.
- 체크섬이 통과됩니다.

```xml
<!-- Germany Driver's License Number -->
<Entity id="91da9335-1edb-45b7-a95f-5fe41a16c63c" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_drivers_license" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_drivers_license_number" />
          <Match idRef="Keyword_german_drivers_license_collaborative" />
          <Match idRef="Keyword_german_drivers_license" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_german_drivers_license_number"></a>Keyword_german_drivers_license_number

- Führerschein
- Fuhrerschein
- Fuehrerschein
- Führerscheinnummer
- Fuhrerscheinnummer
- Fuehrerscheinnummer
- Führerschein- 
- Fuhrerschein- 
- Fuehrerschein- 
- FührerscheinnummerNr
- FuhrerscheinnummerNr
- FuehrerscheinnummerNr
- FührerscheinnummerKlasse
- FuhrerscheinnummerKlasse
- FuehrerscheinnummerKlasse
- Führerschein- Nr
- Fuhrerschein- Nr
- Fuehrerschein- Nr 
- Führerschein- Klasse 
- Fuhrerschein- Klasse 
- Fuehrerschein- Klasse
- FührerscheinnummerNr 
- FuhrerscheinnummerNr 
- FuehrerscheinnummerNr 
- FührerscheinnummerKlasse 
- FuhrerscheinnummerKlasse 
- FuehrerscheinnummerKlasse 
- Führerschein- Nr 
- Fuhrerschein- Nr 
- Fuehrerschein- Nr 
- Führerschein- Klasse 
- Fuhrerschein- Klasse 
- Fuehrerschein- Klasse 
- DL 
- 된다
- Driv Lic 
- Driv Licen 
- Driv License
- Driv Licenses 
- Driv Licence 
- Driv Licences 
- Driv Lic 
- Driver Licen 
- Driver License 
- Driver Licenses 
- Driver Licence 
- Driver Licences 
- Drivers Lic 
- Drivers Licen 
- Drivers License 
- Drivers Licenses 
- Drivers Licence 
- Drivers Licences 
- Driver's Lic 
- Driver's Licen 
- Driver's License 
- Driver's Licenses 
- Driver's Licence 
- Driver's Licences 
- Driving Lic 
- Driving Licen 
- Driving License 
- Driving Licenses 
- Driving Licence 
- Driving Licences

#### <a name="keyword_german_drivers_license_collaborative"></a>Keyword_german_drivers_license_collaborative

- Veiligheid-Führerschein 
- Veiligheid-Fuhrerschein 
- Veiligheid-Fuehrerschein 
- Führerschein 
- Fuhrerschein 
- Fuehrerschein 
- N-Führerschein 
- N-Fuhrerschein 
- N-Fuehrerschein
- Veiligheid-Führerschein 
- Veiligheid-Fuhrerschein 
- Veiligheid-Fuehrerschein 
- Führerschein 
- Fuhrerschein 
- Fuehrerschein 
- N-Führerschein 
- N-Fuhrerschein 
- N-Fuehrerschein 

#### <a name="keyword_german_drivers_license"></a>Keyword_german_drivers_license

- ausstellungsdatum
- ausstellungsort
- ausstellende behöde
- ausstellende behorde
- ausstellende behoerde

## <a name="germany-identity-card-number"></a>독일 id 카드 번호
- 이 중요 한 정보 유형 엔터티는 EU 국가 식별 번호 중요 한 정보 유형에 포함 되며 독립 실행형 중요 한 정보 유형 엔터티로 사용할 수 있습니다.
- 이 중요 한 정보 유형 엔터티는 EU 주민 등록 번호 또는 해당 ID에 해당 하는 중요 한 정보 유형으로 포함 됩니다.

### <a name="format"></a>형식일

2010 년 11 월 1 일 이후: 9 개 문자 및 숫자

1 월 1987 년 10 월 31 일 (2010:10 자리 숫자)

### <a name="pattern"></a>패턴

2010년 11월 1일 이후:
- 1개 문자(대/소문자 구분 안 함) 
- 8자리 숫자

1 년 4 월 1987 일 ~ 10 2010 월 31 일까 지:
- 10자리 숫자

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 65% 신뢰합니다.
- 정규식 Regex_germany_id_card 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keyword_germany_id_card에서 키워드가 발견 되었습니다.

```xml
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_germany_id_card"></a>Keyword_germany_id_card

- ausweis
- gpid
- 확인과
- identifikation
- identifizierungsnummer
- id 카드
- id 번호
- id-nummer
- 개인 id
- personalausweis
- persönliche id nummer
- persönliche identifikationsnummer
- persönliche-id-nummer


## <a name="germany-passport-number"></a>독일 여권 번호
이 중요 한 정보 유형 엔터티는 EU Passport 번호 중요 한 정보 형식에 포함 되며 독립 실행형 중요 한 정보 유형 엔터티로 사용할 수 있습니다.

### <a name="format"></a>형식일

10자리 숫자 또는 문자

### <a name="pattern"></a>패턴

패턴에는 다음이 모두 포함되어야 합니다.
- 첫 번째 문자는 숫자 또는 (C, F, G, H, J, K) 집합의 문자임 
- 3자리 숫자 
- 5자리 숫자 또는 (C, -H, J-N, P, R, T, V-Z) 집합의 문자 
- 1자리 숫자

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_german_passport 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- 5개의 키워드 목록 중에 포함된 키워드가 발견되었습니다.
- 체크섬이 통과됩니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Func_german_passport_data 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- 5개의 키워드 목록 중에 포함된 키워드가 발견되었습니다.
- 체크섬이 통과됩니다.

```xml
<!-- Germany Passport Number -->
<Entity id="2e3da144-d42b-47ed-b123-fbf78604e52c" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_german_passport" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keyword_german_passport_collaborative" />
          <Match idRef="Keyword_german_passport_number" />
          <Match idRef="Keyword_german_passport1" />
          <Match idRef="Keyword_german_passport2" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_passport_data" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keyword_german_passport_collaborative" />
          <Match idRef="Keyword_german_passport_number" />
          <Match idRef="Keyword_german_passport1" />
          <Match idRef="Keyword_german_passport2" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_german_passport"></a>Keyword_german_passport

- reisepass
- reisepasse
- reisepassnummer
- 여권
- passports

#### <a name="keyword_german_passport_collaborative"></a>Keyword_german_passport_collaborative

- ge삼 부, tsdatum
- ausstellungsdatum
- ausstellungsort

#### <a name="keyword_german_passport_number"></a>Keyword_german_passport_number

Reisepass Veiligheid-Reisepass

#### <a name="keyword_german_passport1"></a>Keyword_german_passport1

Reisepass-Veiligheid

#### <a name="keyword_german_passport2"></a>Keyword_german_passport2

bnationalit

## <a name="germany-tax-identification-number"></a>독일 세금 식별 번호
이 중요 한 정보 유형 엔터티는 EU 세금 식별 번호로 중요 한 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백과 구분 기호를 사용 하지 않고 11 자리 숫자
  
### <a name="pattern"></a>패턴

11 자리 숫자:
  
-  10 자리 숫자 
- 검사 숫자 1 개
    
### <a name="checksum"></a>제외

예
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
  
- 이 함수는 해당  `Func_germany_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_germany_eu_tax_file_number` 찾았습니다. 
    
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 이 함수는 해당  `Func_germany_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
          <Match idRef="Keywords_germany_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_germany_eu_tax_file_number"></a>Keywords_germany_eu_tax_file_number

- identifikationsnummer
- steuer id
- steueridentifikationsnummer
- steuernummer
- tax id

- 세금 식별 아니요
- 세금 식별 번호
- 세금 없음 #
- 세금 없음
- 세금 번호
- 세금 등록 번호
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- 언급 id
- 언급 아니요
- 언급 #
- zinn #
- zinn
- zinnnummer

## <a name="greece-drivers-license-number"></a>그리스 운전 면허 번호
이 중요 한 정보 유형 엔터티는 EU 드라이버의 라이선스 번호 중요 한 정보 유형에 포함 되며 독립 실행형 중요 한 정보 유형 엔터티로 사용할 수 있습니다.

### <a name="format"></a>형식일

공백과 구분 기호를 사용 하지 않고 9 자리 숫자
  
### <a name="pattern"></a>패턴

 9자리 숫자 
  
### <a name="checksum"></a>제외

아니요
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 정규식이 해당  `Regex_greece_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_greece_eu_driver's_license_number` 찾았습니다. 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

**Keywords_greece_eu_driver ' s_license_number**

- dlL #
- driver license
- 드라이버 라이선스 번호
- 드라이버 라이선스
- drivers lic
- drivers license
- drivers licence
- driver's license
- 운전 면허 번호
- 운전 라이선스 번호
- 운전 면허 번호
- dlno #
- δεια οδήγησης
- Adeia odigisis


## <a name="greece-national-id-card"></a>그리스 국가 ID 카드
이 중요 한 정보 유형 엔터티는 EU 국가 식별 번호 중요 한 정보 유형에 포함 되며 독립 실행형 중요 한 정보 유형 엔터티로 사용할 수 있습니다.

### <a name="format"></a>형식일

7-8자리 문자 및 숫자와 대시의 조합

### <a name="pattern"></a>패턴

7자리 문자 및 숫자(이전 형식):
- 1개 문자(그리스어 알파벳의 임의 문자)  
- 대시 1개 
- 6자리 숫자

8자리 문자와 숫자(새로운 형식):
- 그리스어 및 라틴어 알파벳 둘 다에 해당 대문자가 포함된 2개 문자(ABEZHIKMNOPTYX)  
- 대시 1개 
- 6자리 숫자

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- 정규식 Regex_greece_id_card 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keyword_greece_id_card에서 키워드가 발견 되었습니다.

```xml
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_greece_id_card"></a>Keyword_greece_id_card

- 그리스 id
- 그리스 국가 id
- 그리스어 개인 id 카드
- 그리스 경찰서 id
- id 카드
- tautotita
- ταυτότητα
- ταυτότητας

## <a name="greece-passport-number"></a>그리스 여권 번호
이 중요 한 정보 유형 엔터티는 EU (유럽 여권 번호) 중요 한 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백 또는 구분 기호가 없는 7 자리, 두 문자
  
### <a name="pattern"></a>패턴

2개 문자와 7자리 숫자
  
### <a name="checksum"></a>제외

아니요
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 정규식이 해당  `Regex_greece_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_greece_eu_passport_number` 찾았습니다. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

**Keywords_greece_eu_passport_number**

- passport number
- 그리스 여권 번호
- passport 아니요
- διαβατηριο

## <a name="greece-tax-identification-number"></a>그리스 세금 식별 번호
이 중요 한 정보 유형 엔터티는 EU 세금 식별 번호로 중요 한 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백과 구분 기호를 사용 하지 않고 9 자리 숫자
  
### <a name="pattern"></a>패턴

9자리 숫자
  
### <a name="checksum"></a>제외

해당 사항 없음
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 정규식이 해당  `Regex_greece_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
- From 키워드를  `Keywords_greece_eu_tax_file_number` 찾았습니다. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_greece_eu_tax_file_number"></a>Keywords_greece_eu_tax_file_number

- afm #
- afm
- aφμ | aφμ αριθμός
- aφμ
- tax id

- 세금 식별 아니요
- 세금 식별 번호
- 세금 없음 #
- 세금 없음
- 세금 번호
- 세금 등록 번호
- 세금 레지스트리 번호
- 세금 레지스트리 번호
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- taxregistryno #
- 언급 id
- 언급 아니요
- 언급 #
- αριθμός φορολογικού μητρώου
- τον αριθμό φορολογικού μητρώου
- φορολογικού μητρώου νο


## <a name="hong-kong-identity-card-hkid-number"></a>HKID (홍콩 id 카드) 번호

### <a name="format"></a>형식일

8-9자리 문자 및 숫자와 마지막 문자를 선택적 괄호로 묶어서 조합

### <a name="pattern"></a>패턴

8-9자리 문자 조합:
- 1-2개 문자(대/소문자 구분 안 함) 
- 6자리 숫자 
- 검사 숫자에 해당하고 선택적으로 괄호로 묶는 마지막 문자(임의 숫자 또는 문자 A)

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Func_hong_kong_id_card 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keyword_hong_kong_id_card에서 키워드가 발견 되었습니다.
- 체크섬이 통과됩니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 65% 신뢰합니다.
- Func_hong_kong_id_card 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- 체크섬이 통과됩니다.

```xml
<!-- Hong Kong Identity Card (HKID) number -->
<Entity id="e63c28a7-ad29-4c17-a41a-3d2a0b70fd9c" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_hong_kong_id_card"/>
     <Match idRef="Keyword_hong_kong_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Func_hong_kong_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_hong_kong_id_card"></a>Keyword_hong_kong_id_card

- hkid
- 홍콩 특별 식별자 카드
- HKIDC
- id card
- identity card
- zh-hk id 카드
- 홍콩 id
- 香港身份證
- 香港永久性居民身份證
- 身份證
- 身份証
- 身分證
- 身分証
- 香港身份証
- 香港身分證
- 香港身分証
- 香港身份證
- 香港居民身份證
- 香港居民身份証
- 香港居民身分證
- 香港居民身分証
- 香港永久性居民身份証
- 香港永久性居民身分證
- 香港永久性居民身分証
- 香港永久性居民身份證
- 香港非永久性居民身份證
- 香港非永久性居民身份証
- 香港非永久性居民身分證
- 香港非永久性居民身分証
- 香港特別行政區永久性居民身份證
- 香港特別行政區永久性居民身份証
- 香港特別行政區永久性居民身分證
- 香港特別行政區永久性居民身分証
- 香港特別行政區非永久性居民身份證
- 香港特別行政區非永久性居民身份証
- 香港特別行政區非永久性居民身分證
- 香港特別行政區非永久性居民身分証
   
## <a name="hungary-drivers-license-number"></a>헝가리어 운전 면허 번호
이 중요 한 정보 유형 엔터티는 EU 드라이버의 라이선스 번호 중요 정보 유형 에서만 사용할 수 있습니다.

### <a name="format"></a>형식일

2 개의 문자 다음에 6 자리 숫자
  
### <a name="pattern"></a>패턴

2 개의 문자와 6 자리 숫자:
  
- 2 개 문자 (대/소문자 구분 안 함) 
- 6자리 숫자
    
### <a name="checksum"></a>제외

아니요
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 정규식이 해당  `Regex_hungary_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_hungary_eu_driver's_license_number` 찾았습니다. 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

**Keywords_hungary_eu_driver ' s_license_number**
- dl #
- driver license
- 드라이버 라이선스 번호
- 드라이버 라이선스
- drivers lic
- drivers license
- drivers licence
- driver's license
- 운전 면허 번호
- 운전 라이선스 번호
- 운전 면허 번호
- dlno #
- vezetoi

## <a name="hungary-national-identification-number"></a>헝가리어 국가 식별 번호
이 중요 한 정보 유형 엔터티는 EU 국가 식별 번호 중요 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

11자리 숫자
  
### <a name="pattern"></a>패턴

11자리 숫자:
  
-  성별에 해당 하는 1 자리 숫자 (1gb, 2 암, 기타 번호는 두 개를 포함 하는 경우 1900에만 발생 합니다. 
- 생년월일에 해당 하는 6 자리 숫자 (YYMMDD)
- 일련 번호에 해당 하는 3 자리 숫자
- 검사 숫자 1 개
    
### <a name="checksum"></a>제외

예
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
  
- 이 함수는 해당  `Func_hungary_eu_national_id_card` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_hungary_eu_national_id_card` 찾았습니다. 
    
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 이 함수는 해당  `Func_hungary_eu_national_id_card` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
```xml
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
          <Match idRef="Keywords_hungary_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
</Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_hungary_eu_national_id_card"></a>Keywords_hungary_eu_national_id_card

- id 번호
- identification number

- sz ig
- sz.ig.
- sz ig
- személyazonosító igazolvány
- személyi igazolvány

## <a name="hungary-passport-number"></a>헝가리어 여권 번호
이 중요 한 정보 유형 엔터티는 EU (유럽 여권 번호) 중요 한 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백 또는 구분 기호가 없는 2 개 문자 및 6 자리 숫자
  
### <a name="pattern"></a>패턴

2 개의 문자 다음에 6 개 또는 7 개의 숫자
  
### <a name="checksum"></a>제외

아니요
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 정규식이 해당  `Regex_hungary_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_hungary_eu_passport_number` 찾았습니다. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```
### <a name="keywords"></a>키워드

**Keywords_hungary_eu_passport_number**

- passport number
- 헝가리어 여권 번호
- passport 아니요
- útlevél száma

## <a name="hungary-social-security-number-or-equivalent-identification"></a>헝가리어 주민 등록 번호 또는 해당 식별자
이 중요 한 정보 유형 엔터티는 EU 주민 등록 번호 또는 해당 ID 중요 정보 유형에 서만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백과 구분 기호를 사용 하지 않고 9 자리 숫자
  
### <a name="pattern"></a>패턴

9자리 숫자
  
### <a name="checksum"></a>제외

예
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
  
- 이 함수는 해당  `Func_hungary_eu_ssn_or_equivalent` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_hungary_eu_ssn_or_equivalent` 찾았습니다. 
    
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 이 함수는 해당  `Func_hungary_eu_ssn_or_equivalent` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_hungary_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_hungary_eu_ssn_or_equivalent"></a>Keywords_hungary_eu_ssn_or_equivalent

- 헝가리어 주민 등록 번호
- social security number
- 사회 alsecuritynumber #
- hssn #
- socialsecuritynno
- hssn
- taj
- taj #
- ssn
- ssn #
- 소셜 보안 아니요
- áfa
- közösségi adószám
- általános forgalmi adó
- hozzáadottérték adó
- áfa szám
- magyar áfa szám


## <a name="hungary-tax-identification-number"></a>헝가리어 세금 식별 번호
이 중요 한 정보 유형 엔터티는 EU 세금 식별 번호로 중요 한 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백이 나 구분 기호가 없는 10 자리 숫자
  
### <a name="pattern"></a>패턴

10 자리 숫자:
  
-  "8" 이어야 하는 1 자리 숫자 
- 날짜 01/01/1867과 개별 생년월일 사이의 일 수에 해당 하는 5 자리 숫자입니다.
- 같은 날에 태어난 사람을 구별 하기 위해 기회가 만든 번호에 해당 하는 3 자리 숫자
- 검사 숫자 1 개
    
### <a name="checksum"></a>제외

예
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
  
- 이 함수는 해당  `Func_hungary_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_hungary_eu_tax_file_number` 찾았습니다. 
    
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 이 함수는 해당  `Func_hungary_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
          <Match idRef="Keywords_hungary_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_hungary_eu_tax_file_number"></a>Keywords_hungary_eu_tax_file_number

- adóazonosító szám
- adóhatóság szám
- adószám
- 헝가리어 언급
- hungatiantin #
- 세금 기관 아니요
- tax id

- 세금 식별 아니요
- 세금 식별 번호
- 세금 없음 #
- 세금 없음
- 세금 번호
- 세금 등록 번호
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- 언급 id
- 언급 아니요
- 언급 #
- vat 번호

## <a name="india-permanent-account-number-pan"></a>인도 (영구 계정 번호)

### <a name="format"></a>형식일

10자리 문자 또는 숫자

### <a name="pattern"></a>패턴

10자리 문자 또는 숫자:
- 5개 문자(대/소문자 구분 안 함)  
- 4자리 숫자 
- 알파벳 검사 숫자에 해당하는 문자 1개

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- 정규식 Regex_india_permanent_account_number 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keyword_india_permanent_account_number에서 키워드가 발견 되었습니다.
- 체크섬이 통과됩니다.

```xml
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_india_permanent_account_number"></a>Keyword_india_permanent_account_number

- Permanent Account Number 
- 확대 
   
## <a name="india-unique-identification-aadhaar-number"></a>Aadhaar (인도 고유 식별) 번호

### <a name="format"></a>형식일

선택적 공백 또는 대시를 포함하는 12자리 숫자

### <a name="pattern"></a>패턴

12자리 숫자:
- 4자리 숫자 
- 선택적 공백 또는 대시  
- 4자리 숫자 
- 선택적 공백 또는 대시  
- 검사 숫자에 해당하는 마지막 숫자

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 300 Func_india_aadhaar 문자에 근접 한 경우에는이 유형의 중요 한 정보를 검색 하는 것으로 85% 확신 합니다.
Keyword_india_aadhar에서 키워드가 발견 되었습니다.
체크섬이 통과됩니다.
DLP 정책은 300 Func_india_aadhaar 문자에 근접 한 경우에는이 유형의 중요 한 정보를 검색 하는 것으로 75% 확신 합니다.
체크섬이 통과됩니다.
```xml
<!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_india_aadhaar"/>
     <Match idRef="Keyword_india_aadhar"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_india_aadhaar"/>
  </Pattern>
</Entity>
```
### <a name="keywords"></a>키워드
   
#### <a name="keyword_india_aadhar"></a>Keyword_india_aadhar
- Aadhar
- Aadhaar
- UID
- आधार
   
## <a name="indonesia-identity-card-ktp-number"></a>인도네시아 id 카드 (KTP) 번호

### <a name="format"></a>형식일

선택적으로 마침표를 포함하는 16자리 숫자

### <a name="pattern"></a>패턴

16자리 숫자:
- 2자리 시/도 코드  
- 마침표(옵션)  
- 2자리 지역 또는 구/군/시 코드  
- 2자리 소구역 코드  
- 마침표(옵션)  
- 생년월일에 해당하는 DDMMYY 형식의 6자리 숫자  
- 마침표(옵션)  
- 4자리 숫자

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- 정규식 Regex_indonesia_id_card 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keyword_indonesia_id_card에서 키워드가 발견 되었습니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- 정규식 Regex_indonesia_id_card 해당 패턴과 일치 하는 콘텐츠를 찾습니다.

```xml
<!-- Indonesia Identity Card (KTP) Number -->
<Entity id="da68fdb0-f383-4981-8c86-82689d3b7d55" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_indonesia_id_card"/>
     <Match idRef="Keyword_indonesia_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_indonesia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드
   
#### <a name="keyword_indonesia_id_card"></a>Keyword_indonesia_id_card

- KTP
- Kartu Tanda Penduduk 
- Nomor Induk Kependudukan 
   
## <a name="international-banking-account-number-iban"></a>IBAN (국제 은행 계좌 번호)

### <a name="format"></a>형식일

국가 코드 (두 문자) + 검사 숫자 (2 자리 숫자)와 bban 숫자 (최대 30 자)

### <a name="pattern"></a>패턴

패턴에는 다음이 모두 포함되어야 합니다.

- 두 글자로 된 국가 코드
- 두 개의 검사 숫자 (선택적 공백) 
- 1-7 개 문자 또는 숫자의 그룹 (공백으로 구분 가능)
- 1-3 문자 또는 숫자

각 국가의 형식은 약간 다릅니다. IBAN 중요 한 정보 유형은 다음과 같은 60 국가를 포함 합니다.

ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, to, do, ee, es, fi,,, fr, gb, ge, gi, gl, gr, hr, hu, kw, il, vg,, nl-nl, tn,,,,,,,,, </c12>,,,,,,,,,,,,, rs, l, se, si,

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_iban 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- 체크섬이 통과됩니다.

```xml
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

없음

   

   
## <a name="international-classification-of-diseases-icd-10-cm"></a>Diseases의 국제 분류 (ICD-10-CM)

### <a name="format"></a>형식일

사전

### <a name="pattern"></a>패턴

Keyword

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Dictionary_icd_10_updated에서 키워드가 발견 되었습니다.
- Dictionary_icd_10_codes에서 키워드가 발견 되었습니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- 업데이트 된 Dictionary_icd_10_ 키워드를 찾았습니다.

```xml
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_updated" />
          <Match idRef="Dictionary_icd_10_codes" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Dictionary_icd_10_updated" />
        </Pattern>

```

키워드

[Diseases의 국제 분류, 10 번째 개정판, 임상 수정 (icd-10CM)](https://go.microsoft.com/fwlink/?linkid=852604)을 기반으로 하는 Dictionary_icd_10_updated 키워드 사전의 모든 용어입니다. 이 유형은 보험 코드가 아니라 용어에 대해서만 찾습니다.

[Diseases의 국제 분류, 10 번째 개정판, 임상 수정 (icd-10CM)](https://go.microsoft.com/fwlink/?linkid=852604)을 기반으로 하는 Dictionary_icd_10_codes 키워드 사전의 모든 용어입니다. 이 유형은 설명에 해당 하는 보험 코드 에서만 찾습니다.

## <a name="international-classification-of-diseases-icd-9-cm"></a>Diseases의 국제 분류 (ICD-9-CM)

### <a name="format"></a>형식일

사전

### <a name="pattern"></a>패턴

Keyword

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Dictionary_icd_9_updated에서 키워드가 발견 되었습니다.
- Dictionary_icd_9_codes에서 키워드가 발견 되었습니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Dictionary_icd_9_updated에서 키워드가 발견 되었습니다.

```xml
    <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_updated" />
          <Match idRef="Dictionary_icd_9_codes" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Dictionary_icd_9_updated" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

[Diseases, 아홉 번째 Revision, 임상 수정 (icd-9CM)의 국가별 분류](https://go.microsoft.com/fwlink/?linkid=852605)를 기반으로 하는 Dictionary_icd_9_updated 키워드 사전의 모든 용어입니다. 이 유형은 보험 코드가 아니라 용어에 대해서만 찾습니다.

[Diseases, 아홉 번째 Revision, 임상 수정 (icd-9CM)의 국가별 분류](https://go.microsoft.com/fwlink/?linkid=852605)를 기반으로 하는 Dictionary_icd_9_codes 키워드 사전의 모든 용어입니다. 이 유형은 설명에 해당 하는 보험 코드 에서만 찾습니다.

## <a name="ip-address"></a>IP 주소

### <a name="format"></a>형식일

#### <a name="ipv4"></a>IPv4
IPv4 주소의 서식 있는 버전(마침표 있음) 및 서식 없는 버전(마침표 없음)으로 구성된 복잡한 패턴

#### <a name="ipv6"></a>IPv6
서식 있는(콜론 포함) IPv6 번호로 구성된 복잡한 패턴

### <a name="pattern"></a>패턴

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

IPv6의 경우 DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Regex_ipv6_address 정규식이 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_ipaddress의 키워드가 발견되지 않았습니다.

IPv4의 경우 DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 95% 신뢰합니다.
- Regex_ipv4_address 정규식이 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_ipaddress의 키워드가 발견되었습니다.

IPv6의 경우 DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 95% 신뢰합니다.
- Regex_ipv6_address 정규식이 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_ipaddress의 키워드가 발견되지 않았습니다.

```xml
    <!-- IP Address -->
    <Entity id="1daa4ad5-e2dd-4ca4-a788-54722c09efb2" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv4_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_ipaddress"></a>Keyword_ipaddress

- IP(이 키워드는 대/소문자를 구분함)
- ip address 
- ip addresses
- internet protocol
- IP-כתובת ה 

## <a name="ireland-drivers-license-number"></a>아일랜드 운전 면허 번호
이 중요 한 정보 유형 엔터티는 EU 드라이버의 라이선스 번호 중요 정보 유형 에서만 사용할 수 있습니다.

### <a name="format"></a>형식일

6 자리 숫자와 4 개 문자
  
### <a name="pattern"></a>패턴

6 자리 숫자와 4 개 문자:
  
- 6자리 숫자
- 4 개 문자 (대/소문자 구분 안 함)
    
### <a name="checksum"></a>제외

아니요
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 정규식이 해당  `Regex_ireland_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_ireland_eu_driver's_license_number` 찾았습니다. 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

**Keywords_ireland_eu_driver ' s_license_number**

- dl #
- driver license
- 드라이버 라이선스 번호
- 드라이버 라이선스
- drivers lic
- drivers license
- drivers licence
- driver's license
- 운전 면허 번호
- 운전 라이선스 번호
- 운전 면허 번호
- dlno #
- ceadúnas tiomána

## <a name="ireland-national-identification-number"></a>아일랜드 국가 식별 번호
이 중요 한 정보 유형 엔터티는 EU 국가 식별 번호 중요 정보 형식에만 포함 됩니다.

### <a name="format"></a>형식일

지정 된 패턴에서 문자, 숫자 및 공백의 9 자 조합
  
### <a name="pattern"></a>패턴

지정 된 패턴에서 문자, 숫자 및 공백의 9 자 조합
  
01 년 1 월 2013 일 현재 위치:
  
-  7자리 숫자 
- 검사 숫자 1 개
- 1 개의 공백 또는 대문자 "W" (대/소문자 구분)
    
01 년 1 월 2013 일 이전:
  
- 7자리 숫자 
- 검사 숫자 1 개
- 1 개의 공백 또는 대문자 (대/소문자 구분)
    
### <a name="checksum"></a>제외

예
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
  
- 이 함수는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- From 키워드를 찾았습니다.
    
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 이 함수는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
    
```xml
 <!--Ireland national identification number  -->
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_eu_national_id_card" />
          <Match idRef="Keywords_ireland_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_ireland_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_ireland_eu_national_id_card"></a>Keywords_ireland_eu_national_id_card

- 클라이언트 id 서비스
- identification number

- 개인 id 번호
- 개인 공용 서비스 번호
- 개인 서비스 없음
- phearsanta seirbhíse poiblí
- pps 아니요
- pps 번호
- pps 서비스 없음
- pps uimh
- ppsn
- ppsno #
- ppsno
- 공용 서비스 없음
- publicserviceno #
- publicserviceno
- 수입 및 주민 등록 보험 번호
- rsi 아니요
- rsi 번호
- rsin
- seirbhís aitheantais client
- uimhpsp
- uimhir aitheantais chánach
- uimhir aitheantais phearsanta
- uimhir phearsanta seirbhíse poiblí

## <a name="ireland-passport-number"></a>아일랜드 여권 번호
이 중요 한 정보 유형 엔터티는 EU (유럽 여권 번호) 중요 한 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백이 나 구분 기호가 없는 두 개의 문자 또는 숫자와 7 자리 숫자
  
### <a name="pattern"></a>패턴

두 개의 문자 또는 숫자와 7 자리 숫자:
  
- 2자리 숫자 또는 문자(대/소문자 구분 안 함)
- 7자리 숫자
    
### <a name="checksum"></a>제외

아니요
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 정규식이 해당  `Regex_ireland_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_ireland_eu_passport_number` 찾았습니다. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

**Keywords_ireland_eu_passport_number**

- passport number
- 아일랜드 여권 번호
- passport 아니요
- pas
- 여권
- 포트
- 포트 numero

## <a name="ireland-personal-public-service-pps-number"></a>아일랜드 PPS (개인 공개 서비스) 번호

### <a name="format"></a>형식일

이전 형식 (31 년 12 월 2012 일까지):
- 7자리 숫자와 1-2개 문자  

새 형식 (1 년 1 월 2013 및 이후):
- 7자리 숫자와 2개 문자

### <a name="pattern"></a>패턴

이전 형식 (31 년 12 월 2012 일까지):
- 7자리 숫자 
- 1-2개 문자(대/소문자 구분 안 함) 

새 형식 (1 년 1 월 2013 및 이후):
- 7자리 숫자 
- 알파벳 검사 숫자에 해당하는 문자 1개(대/소문자 구분 안 함)  
- 문자 "A" 또는 "H"(대/소문자 구분 안 함)

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_ireland_pps 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- 다음 중 하나가 충족됩니다.
    - Keyword_ireland_pps에서 키워드가 발견 되었습니다.
    - Func_eu_date 함수가 올바른 날짜 형식의 날짜를 찾습니다.
- 체크섬이 통과됩니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 65% 신뢰합니다.
- Func_ireland_pps 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- 체크섬이 통과됩니다.

```xml
<!-- Ireland Personal Public Service (PPS) Number -->
<Entity id="1cdb674d-c19a-4fcf-9f4b-7f56cc87345a" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_ireland_pps"/>
     <Any minMatches="1">
  <Match idRef="Keyword_ireland_pps"/>
  <Match idRef="Func_eu_date"/>
     </Any>
  </Pattern>
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Func_ireland_pps"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_ireland_pps"></a>Keyword_ireland_pps

- Personal Public Service Number 
- PPS Number 
- PPS Num 
- PPS No. 
- PPS # 
- .PPS # 
- PPSN 
- Public Services Card 
- Uimhir Phearsanta Seirbhíse Poiblí 
- Uimh PSP 
- PSP 


## <a name="ireland-tax-identification-number"></a>아일랜드 세금 식별 번호
이 중요 한 정보 유형 엔터티는 EU 세금 식별 번호로 중요 한 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백 또는 구분 기호가 없는 7 자리 숫자와 문자
  
### <a name="pattern"></a>패턴

7 자리 숫자와 문자
  
- 7자리 숫자 
- 1 개 문자 (대/소문자 구분 안 함)
    
### <a name="checksum"></a>제외

해당 사항 없음
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
  
- 이 함수는 해당  `Func_ireland_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_ireland_eu_tax_file_number` 찾았습니다. 
    
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 이 함수는 해당  `Func_ireland_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
          <Match idRef="Keywords_ireland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_ireland_eu_tax_file_number"></a>Keywords_ireland_eu_tax_file_number

- 클라이언트 id 서비스
- identification number

- 개인 id 번호
- 개인 공용 서비스 번호
- 개인 서비스 없음
- phearsanta seirbhíse poiblí
- pps 아니요
- pps 번호
- pps 서비스 없음
- pps uimh
- ppsn
- ppsno #
- ppsno
- 공용 서비스 없음
- publicserviceno #
- publicserviceno
- 수입 및 주민 등록 보험 번호
- rsi 아니요
- rsi 번호
- rsin
- seirbhís aitheantais client
- uimhpsp
- uimhir aitheantais chánach
- uimhir aitheantais phearsanta
- uimhir phearsanta seirbhíse poiblí


## <a name="israel-bank-account-number"></a>이스라엘 은행 계좌 번호

### <a name="format"></a>형식일

13자리 숫자

### <a name="pattern"></a>패턴

서식이
- 2자리 숫자 
- 대시 1개 
- 3자리 숫자 
- 대시 1개 
- 8자리 숫자

서식
- 13자리 연속 숫자

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Regex_israel_bank_account_number 정규식이 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_israel_bank_account_number의 키워드가 발견되었습니다.

```xml
<!-- Israel Bank Account Number -->
<Entity id="7d08b2ff-a0b9-437f-957c-aeddbf9b2b25" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_israel_bank_account_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_israel_bank_account_number" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_israel_bank_account_number"></a>Keyword_israel_bank_account_number

- Bank Account Number 
- Bank Account 
- Account Number 
- מספר חשבון בנק 
   
## <a name="israel-national-identification-number"></a>이스라엘 국내 식별 번호

### <a name="format"></a>형식일

9자리 숫자

### <a name="pattern"></a>패턴

9자리 연속 숫자

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Func_israeli_national_id_number 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_Israel_National_ID의 키워드가 발견되었습니다.
- 체크섬이 통과됩니다.

```xml
<!-- Israel National ID Number -->
<Entity id="e05881f5-1db1-418c-89aa-a3ac5c5277ee" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_israeli_national_id_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_Israel_National_ID" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_israel_national_id"></a>Keyword_Israel_National_ID

- מספר זהות 
- National ID Number
   
## <a name="italy-drivers-license-number"></a>이탈리아 운전 면허 번호
이 중요 한 정보 유형 엔터티는 EU 드라이버의 라이선스 번호 중요 한 정보 유형에 포함 되며 독립 실행형 중요 한 정보 유형 엔터티로 사용할 수 있습니다.

### <a name="format"></a>형식일

10개의 문자 및 숫자 조합

### <a name="pattern"></a>패턴

- 10개의 문자 및 숫자 조합:
- 1개 문자(대/소문자 구분 안 함) 
- 문자 "A" 또는 "V"(대/소문자 구분 안 함) 
- 7개 문자(대/소문자 구분 안 함), 숫자 또는 밑줄 문자 
- 1개 문자(대/소문자 구분 안 함)

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Regex_italy_drivers_license_number 정규식이 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_italy_drivers_license_number의 키워드가 발견되었습니다.

```xml
<!-- Italy Driver's license Number -->
<Entity id="97d6244f-9157-41bd-8e0c-9d669a5c4d71" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_italy_drivers_license_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_italy_drivers_license_number" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_italy_drivers_license_number"></a>Keyword_italy_drivers_license_number

- numero di patente di guida 
- patente di guida 

## <a name="italy-national-identification-number"></a>이탈리아 국가 식별 번호
이 중요 한 정보 유형 엔터티는 EU 국가 식별 번호 중요 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

지정 된 패턴에 해당 하는 문자 및 숫자의 16 자 조합
  
### <a name="pattern"></a>패턴

문자와 숫자의 16 자 조합:
  
- 가족 이름에서 처음 세 개의 자음에 해당 하는 3 개의 문자
- 이름의 첫 번째, 세 번째 및 네 번째 자음에 해당 하는 3 개의 문자
- 출생 연도의 마지막 자리에 해당 하는 2 자리 숫자
- 출생 월의 문자에 해당 하는 한 문자는 알파벳 순서로 사용 되지만 1 ~ E, H, L, M, P, R에 해당 하는 문자를 사용 하는 경우에만 사용할 수 있습니다.
- Genders를 구분 하기 위해 출생 달의 날짜에 해당 하는 2 자리 숫자 (40)가 여성 생년월일에 추가 되었습니다.
- 사용자가 태어난 municipality 관련 지역 번호에 해당 하는 4 자리 숫자 (국가 전체 코드는 외국 국가에 사용 됨)
- 1 개의 패리티 숫자
    
### <a name="checksum"></a>제외

예
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
  
- 이 함수는 해당  `Func_italy_eu_national_id_card` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_italy_eu_national_id_card` 찾았습니다. 
    
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 이 함수는 해당  `Func_italy_eu_national_id_card` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
```xml
<!-- Italy national identification number -->
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
          <Match idRef="Keywords_italy_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_italy_eu_national_id_card"></a>Keywords_italy_eu_national_id_card

- codice 회계
- codice
- codice id personale
- codice personale
- 회계 코드
- numero certificato personale
- numero di identificazione fiscale
- numero id personale
- numero personale
- 개인 인증서 번호
- 개인 코드
- 개인 id 코드
- 개인 id 번호
- personalcodeno #
- 세금 코드
- tax id

- 세금 식별 아니요
- 세금 식별 번호
- 세금 id 번호
- 세금 없음 #
- 세금 없음
- 세금 번호
- 세금 등록 번호
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- 언급 id
- 언급 아니요
- 언급 #

## <a name="italy-passport-number"></a>이탈리아 여권 번호
이 중요 한 정보 유형 엔터티는 EU (유럽 여권 번호) 중요 한 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백이 나 구분 기호가 없는 두 개의 문자 또는 숫자와 7 자리 숫자
  
### <a name="pattern"></a>패턴

두 개의 문자 또는 숫자와 7 자리 숫자:
  
- 2자리 숫자 또는 문자(대/소문자 구분 안 함)
- 7자리 숫자
    
### <a name="checksum"></a>제외

해당 사항 없음
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 정규식이 해당  `Regex_italy_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_italy_eu_passport_number` 찾았습니다. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

**Keywords_italy_eu_passport_number**

- 이탈리아 여권 번호
- repubblica italiana passaporto
- passaporto
- passaporto italiana
- passport number
- italiana passaporto numero
- passaporto numero
- numéro) 포트 italien
- numéro (고) 포트

## <a name="italy-tax-identification-number"></a>이탈리아 세금 식별 번호
이 중요 한 정보 유형 엔터티는 EU 세금 식별 번호로 중요 한 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

지정 된 패턴의 문자와 숫자 16 개
  
### <a name="pattern"></a>패턴

16 자의 문자 및 숫자:
  
-  가족 이름에서 처음 세 개의 자음에 해당 하는 3 개의 문자 
- 이름의 첫 번째, 세 번째 및 네 번째 자음에 해당 하는 3 개의 문자
- 출생 연도의 마지막 자리에 해당 하는 2 자리 숫자
- 출생 달에 해당 하는 1 자리 숫자는 알파벳 순으로 사용 되지만 A에서 E, H, L, M, P, R에 해당 하는 문자만 사용 되며, 따라서 1 월은 A와 10 월이 됩니다.
- 남성의와 구별 하기 위해 여성의 경우 짝수에서 출생 일에 40이 추가 되는 출생 달의 날짜에 해당 하는 2 자리 숫자
- 사용자가 태어난 municipality 관련 지역 번호에 해당 하는 4 자리 숫자-국가 전체 코드를 외국 국가에 사용 합니다.
- 검사 숫자 1 개
    
### <a name="checksum"></a>제외

예
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
  
- 이 함수는 해당  `Func_italy_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_italy_eu_tax_file_number` 찾았습니다. 
    
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 이 함수는 해당  `Func_italy_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
          <Match idRef="Keywords_italy_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_italy_eu_tax_file_number"></a>Keywords_italy_eu_tax_file_number

- codice 회계
- codice
- codice id personale
- codice personale
- 회계 코드
- numero certificato personale
- numero di identificazione fiscale
- numero id personale
- numero personale
- 개인 인증서 번호
- 개인 코드
- 개인 id 코드
- 개인 id 번호
- personalcodeno #
- 세금 코드
- tax id

- 세금 식별 아니요
- 세금 식별 번호
- 세금 id 번호
- 세금 없음 #
- 세금 없음
- 세금 번호
- 세금 등록 번호
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- 언급 id
- 언급 아니요
- 언급 #


## <a name="japan-bank-account-number"></a>일본 은행 계좌 번호

### <a name="format"></a>형식일

7 또는 8자리 숫자

### <a name="pattern"></a>패턴

은행 계좌 번호:
- 7 또는 8자리 숫자
- 은행 계좌 지점 코드:
- 4자리 숫자 
- 공백 또는 대시(선택 사항) 
- 3자리 숫자

제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_jp_bank_account 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_jp_bank_account의 키워드가 발견되었습니다.
- 다음 중 하나가 충족됩니다.
- Func_jp_bank_account_branch_code 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_jp_bank_branch_code의 키워드가 발견되었습니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Func_jp_bank_account 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_jp_bank_account의 키워드가 발견되었습니다.

```xml
<!-- Japan Bank Account Number -->
<Entity id="d354f95b-96ee-4b80-80bc-4377312b55bc" patternsProximity="300" recommendedConfidence="75">
  <Version minEngineVersion="15.01.0131.000">
    <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_jp_bank_account" />
          <Match idRef="Keyword_jp_bank_account" />
          <Any minMatches="1">
            <Match idRef="Func_jp_bank_account_branch_code" />
            <Match idRef="Keyword_jp_bank_branch_code" />
          </Any>
      </Pattern>
  </Version>    
     <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_bank_account" />
        <Match idRef="Keyword_jp_bank_account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_jp_bank_account"></a>Keyword_jp_bank_account

- Checking Account Number 
- Checking Account 
- Checking Account # 
- Checking Acct Number 
- Checking Acct # 
- Checking Acct No. 
- Checking Account No. 
- Bank Account Number 
- Bank Account 
- Bank Account # 
- Bank Acct Number 
- Bank Acct # 
- Bank Acct No. 
- Bank Account No. 
- Savings Account Number 
- Savings Account 
- Savings Account # 
- Savings Acct Number 
- Savings Acct # 
- Savings Acct No. 
- Savings Account No. 
- Debit Account Number 
- Debit Account 
- Debit Account # 
- Debit Acct Number 
- Debit Acct # 
- Debit Acct No. 
- Debit Account No. 
- 口座番号を当座預金口座の確認 
- #アカウントの確認 、 勘定番号の確認 
- #勘定の確認 
- 勘定番号の確認 
- 口座番号の確認 
- 銀行口座番号 
- 銀行口座 
- 銀行口座＃ 
- 銀行の勘定番号 
- 銀行のacct＃ 
- 銀行の勘定いいえ 
- 銀行口座番号
- 普通預金口座番号 
- 預金口座 
- 貯蓄口座＃ 
- 貯蓄勘定の数 
- 貯蓄勘定＃ 
- 貯蓄勘定番号 
- 普通預金口座番号 
- 引き落とし口座番号 
- 口座番号 
- 口座番号＃ 
- デビットのacct番号 
- デビット勘定＃ 
- デビットACCTの番号 
- デビット口座番号 

#### <a name="keyword_jp_bank_branch_code"></a>Keyword_jp_bank_branch_code

Otemachi

## <a name="japan-drivers-license-number"></a>일본 운전 면허 번호

### <a name="format"></a>형식일

12자리 숫자

### <a name="pattern"></a>패턴

12자리 연속 숫자

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Func_jp_drivers_license_number 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_jp_drivers_license_number의 키워드가 발견되었습니다.

```xml
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_jp_drivers_license_number"></a>Keyword_jp_drivers_license_number

- dl # 
- DL 
- 된다 # 
- 된다 
- driver license 
- driver licenses 
- drivers license 
- driver's license 
- drivers licenses 
- driver's licenses 
- driving licence 
- lic # 
- LIC 
- driver'lics # 
- state id 
- state identification 
- state identification number 
- 低所得国＃ 
- 免許証 
- 状態ID
- 状態の識別 
- 状態の識別番号 
- 運転免許 
- 運転免許証 
- 運転免許証番号 
   
## <a name="japan-passport-number"></a>일본 여권 번호

### <a name="format"></a>형식일

2개 문자와 7자리 숫자

### <a name="pattern"></a>패턴

2개의 문자(대/소문자 구분 안 함)와 7자리 숫자

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Func_jp_passport 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_jp_passport의 키워드가 발견되었습니다.

```xml
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_jp_passport"></a>Keyword_jp_passport

- パスポート 
- パスポート番号 
- パスポートのNum 
- パスポート＃ 

## <a name="japan-residence-card-number"></a>일본 거주지 카드 번호

### <a name="format"></a>형식일

12 개의 문자 및 숫자

### <a name="pattern"></a>패턴

12 개의 문자 및 숫자:
- 2문자(대/소문자 구분 안 함)
- 8자리 숫자 
- 2문자(대/소문자 구분 안 함)

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- 정규식 Regex_jp_residence_card_number 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keyword_jp_residence_card_number에서 키워드가 발견 되었습니다.

```xml
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_jp_residence_card_number"></a>Keyword_jp_residence_card_number

- 거주지 카드 번호
- 거주지 카드 아니요
- 거주지 카드 #
- 在留カード番号

## <a name="japan-resident-registration-number"></a>일본 상주 등록 번호

### <a name="format"></a>형식일

11자리 숫자

### <a name="pattern"></a>패턴

11자리 연속 숫자

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Func_jp_resident_registration_number 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_jp_resident_registration_number의 키워드가 발견되었습니다.

```xml
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_jp_resident_registration_number"></a>Keyword_jp_resident_registration_number

- Resident Registration Number
- Resident Register Number 
- Residents Basic Registry Number 
- Resident Registration No. 
- Resident Register No. 
- Residents Basic Registry No. 
- Basic Resident Register No. 
- 住民登録番号、登録番号をレジデント 
- 住民基本登録番号、登録番号 
- 住民基本レジストリ番号を常駐 
- 登録番号を常駐住民基本台帳登録番号 

   
## <a name="japan-social-insurance-number-sin"></a>일본 SIN (사회 보험 번호)

### <a name="format"></a>형식일

7-12자리 숫자

### <a name="pattern"></a>패턴

7-12자리 숫자:
- 4자리 숫자 
- 하이픈 1개(선택 사항) 
- 6 자리 숫자 또는
- 7-12자리 연속 숫자

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_jp_sin 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_jp_sin의 키워드가 발견되었습니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Func_jp_sin_pre_1997 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_jp_sin의 키워드가 발견되었습니다.

```xml
<!-- Japan Social Insurance Number -->
<Entity id="c840e719-0896-45bb-84fd-1ed5c95e45ff" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_jp_sin" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_sin_pre_1997" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_jp_sin"></a>Keyword_jp_sin

- Social Insurance No. 
- Social Insurance Num 
- Social Insurance Number 
- 社会保険のテンキー 
- 社会保険番号 

## <a name="latvia-drivers-license-number"></a>라트비아 운전 면허 번호
이 중요 한 정보 유형 엔터티는 EU 드라이버의 라이선스 번호 중요 정보 유형 에서만 사용할 수 있습니다.

### <a name="format"></a>형식일

3 개의 문자 및 6 자리 숫자
  
### <a name="pattern"></a>패턴

3 개의 문자 및 6 자리 숫자:
  
-  3 개 문자 (대/소문자 구분 안 함) 
- 6자리 숫자
    
### <a name="checksum"></a>제외

아니요
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 정규식이 해당  `Regex_latvia_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_latvia_eu_driver's_license_number` 찾았습니다. 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

**Keywords_latvia_eu_driver ' s_license_number**

- dl #
- driver license
- 드라이버 라이선스 번호
- 드라이버 라이선스
- drivers lic
- drivers license
- drivers licence
- driver's license
- 운전 면허 번호
- 운전 라이선스 번호
- 운전 면허 번호
- dlno #
- autovadītāja apliecība

## <a name="latvia-national-identification-number"></a>라트비아 국가 식별 번호
이 중요 한 정보 유형 엔터티는 EU 국가 식별 번호 중요 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

지정 된 형식의 11 자리 숫자 및 하이픈
  
### <a name="pattern"></a>패턴

11 자리 숫자와 하이픈:
  
-  생년월일에 해당 하는 6 자리 숫자 (DDMMYY) 
- 하이픈
- 출생 세기에 해당 하는 1 자리 숫자 (19th 세기의 경우 "1", 21 세기의 경우 "2")
- 임의로 생성 되는 4 자리 숫자
    
### <a name="checksum"></a>제외

예
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
  
- 이 함수는 해당  `Func_latvia_eu_national_id_card` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_latvia_eu_national_id_card` 찾았습니다. 
    
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 이 함수는 해당  `Func_latvia_eu_national_id_card` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
```xml
<!-- Latvia national identification number -->
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
          <Match idRef="Keywords_latvia_eu_national_id_card" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_latvia_eu_national_id_card"></a>Keywords_latvia_eu_national_id_card

- 관리 번호
- alvas nē
- 돌 번호
- 시민 번호
- 민사 번호
- 전자 위한 인구 조사 번호
- 전자 번호
- 회계 코드
- 의료 기관 사용자 번호
- i #
- id-코드
- identification number

- identifikācijas numurs
- id-번호
- 개별 번호
- latvija alva
- nacionālais id
- 
national id
- 국가 식별 번호
- 국가 id 번호
- national insurance number

- 국가 레지스터 번호
- nodokļa numurs
- nodokļu id
- nodokļu identifikācija numurs
- 개인 인증서 번호
- 개인 코드
- 개인 id 코드
- 개인 id 번호
- 개인 식별 코드
- 개인 식별자
- 개인 id 번호
- 개인 번호
- 개인 숫자 코드
- personalcodeno #
- 가상 사용자 kods
- 인구 식별 코드
- 공용 서비스 번호
- 
registration number
- 수익 번호
- 사회적 보험 번호
- social security number

- 주 세금 코드
- 세금 파일 번호
- tax id

- 세금 식별 아니요
- 세금 식별 번호
- 세금 없음 #
- 세금 없음
- 세금 번호
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- 언급 id
- 언급 아니요
- 언급 #
- 시킵니다 번호

## <a name="latvia-passport-number"></a>라트비아, 여권 번호
이 중요 한 정보 유형 엔터티는 EU (유럽 여권 번호) 중요 한 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백이 나 구분 기호가 없는 두 개의 문자 또는 숫자와 7 자리 숫자
  
### <a name="pattern"></a>패턴

두 개의 문자 또는 숫자와 7 자리 숫자:
  
- 2자리 숫자 또는 문자(대/소문자 구분 안 함)
- 7자리 숫자
    
### <a name="checksum"></a>제외

아니요
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 정규식이 해당  `Regex_latvia_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_latvia_eu_passport_number` 찾았습니다. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

**Keywords_latvia_eu_passport_number**

- passport number
- 라트비아어 여권 번호
- passport 아니요
- pase numurs    

## <a name="latvia-tax-identification-number"></a>라트비아 세금 번호
이 중요 한 정보 유형 엔터티는 EU 세금 식별 번호로 중요 한 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백이 나 구분 기호가 없는 11 자리 숫자
  
### <a name="pattern"></a>패턴

지정 된 패턴에서 11 자리 숫자
  
- 출생 날짜에 해당 하는 6 자리 숫자 (DDMMYY) 
- 출생 세기에 해당 하는 1 자리 숫자 이며, "0"은 19th 세기에 해당 하 고 "1"은 20th 세기에 해당 하며 21 세기에 해당 합니다.
- 4자리 숫자
    
### <a name="checksum"></a>제외

예
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
  
- 이 함수는 해당  `Func_latvia_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_latvia_eu_tax_file_number` 찾았습니다. 
    
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 이 함수는 해당  `Func_latvia_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
          <Match idRef="Keywords_latvia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_latvia_eu_tax_file_number"></a>Keywords_latvia_eu_tax_file_number

- 관리 번호
- alvas nē
- 돌 번호
- 시민 번호
- 민사 번호
- 전자 위한 인구 조사 번호
- 전자 번호
- 회계 코드
- 의료 기관 사용자 번호
- i #
- id-코드
- identification number

- identifikācijas numurs
- id-번호
- 개별 번호
- latvija alva
- nacionālais id
- 
national id
- 국가 식별 번호
- 국가 id 번호
- national insurance number

- 국가 레지스터 번호
- nodokļa numurs
- nodokļu id
- nodokļu identifikācija numurs
- 개인 인증서 번호
- 개인 코드
- 개인 id 코드
- 개인 id 번호
- 개인 식별 코드
- 개인 식별자
- 개인 id 번호
- 개인 번호
- 개인 숫자 코드
- personalcodeno #
- 가상 사용자 kods
- 인구 식별 코드
- 공용 서비스 번호
- 
registration number
- 수익 번호
- 사회적 보험 번호
- social security number

- 주 세금 코드
- 세금 파일 번호
- tax id

- 세금 식별 아니요
- 세금 식별 번호
- 세금 없음 #
- 세금 없음
- 세금 번호
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- 언급 id
- 언급 아니요
- 언급 #
- 시킵니다 번호

## <a name="lithuania-drivers-license-number"></a>리투아니아 운전 면허 번호
이 중요 한 정보 유형 엔터티는 EU 드라이버의 라이선스 번호 중요 정보 유형 에서만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백과 구분 기호가 없는 8 자리 숫자
  
### <a name="pattern"></a>패턴

 8자리 숫자 
  
### <a name="checksum"></a>제외

아니요
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 정규식이 해당  `Regex_lithuania_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_lithuania_eu_driver's_license_number` 찾았습니다. 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

**Keywords_lithuania_eu_driver ' s_license_number**

- dl #
- driver license
- 드라이버 라이선스 번호
- 드라이버 라이선스
- drivers lic
- drivers license
- drivers licence
- driver's license
- 운전 면허 번호
- 운전 라이선스 번호
- 운전 면허 번호
- dlno #
- vairuotojo pažymėjimas

## <a name="lithuania-national-identification-number"></a>리투아니아 국가 식별 번호
이 중요 한 정보 유형 엔터티는 EU 국가 식별 번호 중요 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백과 구분 기호를 사용 하지 않고 11 자리 숫자
  
### <a name="pattern"></a>패턴

공백과 구분 기호를 사용 하지 않고 11 자리 숫자:
  
- 사용자의 성별 및 출생 세기에 해당 하는 1 자리 숫자
- 생년월일에 해당 하는 6 자리 숫자 (YYMMDD) 
- 출생 날짜의 일련 번호에 해당 하는 3 자리 숫자
- 검사 숫자 1 개
    
### <a name="checksum"></a>제외

예
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
  
- 이 함수는 해당  `Func_lithuania_eu_national_id_card` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_lithuania_eu_national_id_card` 찾았습니다. 
    
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 이 함수는 해당  `Func_lithuania_eu_national_id_card` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
```xml
<!-- Lithuania national identification number -->
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_national_id_card" />
          <Match idRef="Keywords_lithuania_eu_national_id_card" />
        </Pattern> 
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_lithuania_eu_national_id_card"></a>Keywords_lithuania_eu_national_id_card

- as메이 inis kodas
- asmens kodas
- 시민 서비스 번호
- mokesčių id
- mokesčių identifikavimas numeris
- mokesčių identifikavimo numeris
- mokesčių numeris
- 국가 식별 번호
- 개인 코드
- 개인 숫자 코드
- piliečio paslaugos numeris
- tax id

- 세금 식별 아니요
- 세금 식별 번호
- 세금 없음 #
- 세금 없음
- 세금 번호
- 세금 등록 번호
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- 언급 id
- 언급 아니요
- 언급 #
- unikalus identifikavimo kodas
- unikalus identifikavimo numeris
- 고유 id 번호
- 고유 id 번호
- uniqueidentityno #

## <a name="lithuania-passport-number"></a>리투아니아 여권 번호
이 중요 한 정보 유형 엔터티는 EU (유럽 여권 번호) 중요 한 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백이 나 구분 기호가 없는 8 자리 숫자 또는 문자
  
### <a name="pattern"></a>패턴

8 자리 숫자 또는 문자 (대/소문자 구분 안 함)
  
### <a name="checksum"></a>제외

해당 사항 없음
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 정규식이 해당  `Regex_lithuania_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_lithuania_eu_passport_number` 찾았습니다. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

**Keywords_lithuania_eu_passport_number**

여권 번호 lithunian 여권 번호 passport 암호 없음 o numeris

## <a name="lithuania-tax-identification-number"></a>리투아니아 세금 식별 번호
이 중요 한 정보 유형 엔터티는 EU 세금 식별 번호로 중요 한 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백이 나 구분 기호가 없는 11 자리 숫자
  
### <a name="pattern"></a>패턴

11자리 숫자
  
### <a name="checksum"></a>제외

해당 사항 없음
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
  
- 이 함수는 해당  `Func_lithuania_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_lithuania_eu_tax_file_number` 찾았습니다. 
    
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 이 함수는 해당  `Func_lithuania_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
          <Match idRef="Keywords_lithuania_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_lithuania_eu_tax_file_number"></a>Keywords_lithuania_eu_tax_file_number

- as메이 inis kodas
- asmens kodas
- 시민 서비스 번호
- mokesčių id
- mokesčių identifikavimas numeris
- mokesčių identifikavimo numeris
- mokesčių numeris
- 국가 식별 번호
- 개인 코드
- piliečio paslaugos numeris
- tax id

- 세금 식별 아니요
- 세금 식별 번호
- 세금 없음 #
- 세금 없음
- 세금 번호
- 세금 등록 번호
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- 언급 id
- 언급 아니요
- 언급 #
- unikalus identifikavimo kodas
- unikalus identifikavimo numeris
- 고유 id 번호
- 고유 id 번호
- uniqueidentityno #

## <a name="luxemburg-drivers-license-number"></a>룩셈부르크 운전 면허 번호
중요 한 정보 유형 엔터티는 EU 드라이버의 라이선스 번호 중요 정보 유형 에서만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백과 구분 기호가 없는 6 자리 숫자
  
### <a name="pattern"></a>패턴

 6자리 숫자 
  
### <a name="checksum"></a>제외

아니요
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 정규식이 해당  `Regex_luxemburg_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_luxemburg_eu_driver's_license_number` 찾았습니다. 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

**Keywords_luxemburg_eu_driver ' s_license_number**

- dl #
- driver license
- 드라이버 라이선스 번호
- 드라이버 라이선스
- drivers lic
- drivers license
- drivers licence
- driver's license
- 운전 면허 번호
- 운전 라이선스 번호
- 운전 면허 번호
- dlno #
- fahrerlaubnis

## <a name="luxemburg-national-identification-number"></a>룩셈부르크 국가 식별 번호
이 중요 한 정보 유형 엔터티는 EU 국가 식별 번호 중요 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백과 구분 기호를 사용 하지 않고 11 자리 숫자
  
### <a name="pattern"></a>패턴

11자리 숫자
  
- 사용자의 성별 및 출생 세기에 해당 하는 1 자리 숫자
- 생년월일에 해당 하는 6 자리 숫자 (YYMMDD) 
- 출생 날짜의 일련 번호에 해당 하는 3 자리 숫자
- 검사 숫자 1 개
    
### <a name="checksum"></a>제외

해당 사항 없음
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 정규식이 해당  `Regex_luxemburg_eu_national_id_card` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_luxemburg_eu_national_id_card` 찾았습니다. 
    
```xml
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_national_id_card" />
          <Match idRef="Keywords_luxemburg_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_luxemburg_eu_national_id_card"></a>Keywords_luxemburg_eu_national_id_card

- eindeutige id
- eindeutige id-nummer
- eindeutigeid #
- id personnelle
- idpersonnelle #
- idpersonnelle
- 개별 코드
- 개별 id
- 개별 식별
- 개별 id
- numéro d'identification 담당자
- 개인 id
- 개인 식별
- 개인 id
- personalidno #
- personalidnumber #
- persönliche identifikationsnummer
- 고유 id
- 고유 id
- uniqueidkey #

## <a name="luxemburg-passport-number"></a>룩셈부르크 여권 번호
이 중요 한 정보 유형 엔터티는 EU (유럽 여권 번호) 중요 한 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백이 나 구분 기호가 없는 8 자리 숫자 또는 문자
  
### <a name="pattern"></a>패턴

8 자리 숫자 또는 문자 (대/소문자 구분 안 함)
  
### <a name="checksum"></a>제외

아니요
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 정규식이 해당  `Regex_nation_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_nation_eu_passport_number` 찾았습니다. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

**Keywords_nation_eu_passport_number**

여권 번호 라트비아어 여권 passport 번호 passport passnummer

## <a name="luxemburg-tax-identification-number"></a>룩셈부르크 세금 식별 번호
이 중요 한 정보 유형 엔터티는 EU 세금 식별 번호로 중요 한 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백이 나 구분 기호가 없는 13 자리 숫자
  
### <a name="pattern"></a>패턴

13자리 숫자:
  
- 11자리 숫자 
- 2개의 검사 숫자
    
### <a name="checksum"></a>제외

예
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
  
- 이 함수는 해당  `Func_luxemburg_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_luxemburg_eu_tax_file_number` 찾았습니다. 
    
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 이 함수는 해당  `Func_luxemburg_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Match idRef="Keywords_luxemburg_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_luxemburg_eu_tax_file_number"></a>Keywords_luxemburg_eu_tax_file_number

- carte de sécurité 사회 ale
- étain 아님
- étain #
- identifiant d'impôt
- 룩셈부르크 세금 identifikatiounsnummer
- numéro d'étain
- numéro d'identification 회계 luxembourgeois
- numéro d'identification fiscale
- 소셜 보안
- sozialunterstützung
- sozialversécherung
- sozialversicherungsausweis
- steier id
- steier identifikatiounsnummer
- steier nummer
- steuer id
- steueridentifikationsnummer
- steuernummer
- tax id

- 세금 식별 아니요
- 세금 식별 번호
- 세금 없음 #
- 세금 없음
- 세금 번호
- 세금 등록 번호
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- 언급 id
- 언급 아니요
- 언급 #
- zinn #
- zinn
- zinnzahl


## <a name="malaysia-identification-card-number"></a>말레이시아 식별 카드 번호

### <a name="format"></a>형식일

선택적으로 하이픈을 포함하는 12자리 숫자

### <a name="pattern"></a>패턴

12자리 숫자:
- 생년월일에 해당하는 YYMMDD 형식의 6자리 숫자  
- 대시(옵션) 
- 2개 문자로 이루어진 출생지 코드  
- 대시(옵션) 
- 임의의 3자리 숫자  
- 1자리 성별 코드

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- 정규식 Regex_malaysia_id_card_number 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keyword_malaysia_id_card_number에서 키워드가 발견 되었습니다.

```xml
<!-- Malaysia ID Card Number -->
</Entity>
      <Entity id="7f0e921c-9677-435b-aba2-bb8f1013c749" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
            <IdMatch idRef="Regex_malaysia_id_card_number" />
            <Match idRef="Keyword_malaysia_id_card_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드
   
#### <a name="keyword_malaysia_id_card_number"></a>Keyword_malaysia_id_card_number

- 디지털 응용 프로그램 카드
- i/c
- i/c 아니요
- 비용
- ic 아니요
- id card
- 식별 카드
- identity card
- k/p
- k/p 아니요
- kad akuan diri
- kad aplikasi 디지털
- kad pengenalan 말레이시아
- kp
- kp 아니요
- mykad
- mykas
- mykid
- mypr
- myta
- 말레이시아 id 카드
- 말레이지아 id 카드
- nric
- 개인 식별 카드

## <a name="malta-drivers-license-number"></a>몰타 운전 면허 번호
이 중요 한 정보 유형 엔터티는 EU 드라이버의 라이선스 번호 중요 정보 유형 에서만 사용할 수 있습니다.

### <a name="format"></a>형식일

지정 된 패턴에서 두 개의 문자와 6 자리 숫자 조합
  
### <a name="pattern"></a>패턴

두 문자와 6 자리 숫자의 조합:
  
- 2 개 문자 (대/소문자 구분 안 함)
- 공백 1개(선택 사항)
- 3자리 숫자
- 공백 1개(선택 사항)
- 3자리 숫자
    
### <a name="checksum"></a>제외

아니요
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 정규식이 해당  `Regex_malta_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_malta_eu_driver's_license_number` 찾았습니다. 
    
```xml
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

**Keywords_malta_eu_driver ' s_license_number**

- dl #
- driver license
- 드라이버 라이선스 번호
- 드라이버 라이선스
- drivers lic
- drivers license
- drivers licence
- driver's license
- 운전 면허 번호
- 운전 라이선스 번호
- 운전 면허 번호
- dlno #
- liċenzja tas-sewqan

## <a name="malta-national-identification-number"></a>몰타 국내 식별 번호
이 중요 한 정보 유형 엔터티는 EU 국가 식별 번호 중요 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

7 자리 숫자와 문자 1 개
  
### <a name="pattern"></a>패턴

7 자리 숫자와 문자 1 개:
  
-  7자리 숫자 
- 대문자 1 개 (대/소문자 구분)
    
### <a name="checksum"></a>제외

해당 사항 없음
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 정규식이 해당  `Regex_malta_eu_national_id_card` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_malta_eu_national_id_card` 찾았습니다. 
    
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 65% 신뢰합니다.
  
- 정규식이 해당  `Regex_malta_eu_national_id_card` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
```xml
 <!--Malta national identification number  -->
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
          <Match idRef="Keywords_malta_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_malta_eu_national_id_card"></a>Keywords_malta_eu_national_id_card

- 시민 서비스 번호
- id tat-taxxa
- identifika numru tal-biljett
- kodiċi numerali personali
- numru ta ' personali
- numru ta ' taxxa
- numru ta ' uniku
- numru ta ' uniku
- numru taċ-ċittadin
- numru tat
- 개인 숫자 코드
- 고유 id 번호
- 고유 id 번호
- uniqueidentityno #


## <a name="malta-passport-number"></a>몰타 여권 번호
이 중요 한 정보 유형 엔터티는 EU (유럽 여권 번호) 중요 한 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백이 나 구분 기호 없이 7 자리 숫자
  
### <a name="pattern"></a>패턴

 7자리 숫자 
  
### <a name="checksum"></a>제외

아니요
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 정규식이 해당  `Regex_malta_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_malta_eu_passport_number` 찾았습니다. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

**Keywords_malta_eu_passport_number**

- passport number
- 몰타어 여권 번호
- passport 아니요
- numru-passaport

## <a name="malta-tax-identification-number"></a>몰타 세금 식별 번호
이 중요 한 정보 유형 엔터티는 EU 세금 식별 번호로 중요 한 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

몰타어 nationals의 경우 지정 된 패턴의 7 자리 및 한 문자
  
몰타어 이외의 nationals 및 몰타어 엔터티: 9 자리 숫자
  
### <a name="pattern"></a>패턴

몰타어 nationals: 7 자리 숫자 및 1 개 문자
  
-  7자리 숫자 
- 1 개 문자 (대/소문자 구분 안 함)
    
몰타어 이외의 nationals 및 몰타어 엔터티: 9 자리 숫자
  
-  9자리 숫자 
    
### <a name="checksum"></a>제외

해당 사항 없음
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 이 함수는 해당  `Func_malta_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_malta_eu_tax_file_number` 찾았습니다. 
    
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 65% 신뢰합니다.
  
- 이 함수는 해당  `Func_malta_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_malta_eu_tax_file_number" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_malta_eu_tax_file_number"></a>Keywords_malta_eu_tax_file_number

- 시민 서비스 번호
- id tat-taxxa
- identifika numru tal-biljett
- kodiċi numerali personali
- numru ta ' personali
- numru ta ' taxxa
- numru ta ' uniku
- numru ta ' uniku
- numru taċ-ċittadin
- numru tat
- 개인 숫자 코드
- tax id

- 세금 식별 아니요
- 세금 식별 번호
- 세금 없음 #
- 세금 없음
- 세금 번호
- 세금 등록 번호
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- 언급 id
- 언급 아니요
- 언급 #
- 고유 id 번호
- 고유 id 번호
- uniqueidentityno #

## <a name="netherlands-citizens-service-bsn-number"></a>네덜란드 시민 서비스 (BSN) 번호

### <a name="format"></a>형식일

선택적으로 공백을 포함하는 8-9자리 숫자

### <a name="pattern"></a>패턴

8-9자리 숫자:
- 3자리 숫자 
- 공백 1개(선택 사항) 
- 3자리 숫자 
- 공백 1개(선택 사항) 
- 2-3자리 숫자

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_netherlands_bsn 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keyword_netherlands_bsn에서 키워드가 발견 되었습니다.
- Func_eu_date2 함수는 올바른 날짜 형식의 날짜를 찾습니다.
- 체크섬이 통과됩니다.

```xml
<!-- Netherlands Citizen's Service (BSN) Number -->
<Entity id="c5f54253-ef7e-44f6-a578-440ed67e946d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
       <IdMatch idRef="Func_netherlands_bsn" /> 
       <Match idRef="Keyword_netherlands_bsn" /> 
       <Match idRef="Func_eu_date2" /> 
  </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_netherlands_bsn"></a>Keyword_netherlands_bsn
  
- bsn #
- bsn
- burgerservicenummer
- 시민 서비스 번호
- 사용자 번호
- 개인 번호
- 개인 숫자 코드
- 사용자 관련 번호
- persoonlijk nummer
- persoonlijke 코드
- persoonsgebonden
- persoonsnummer
- 사회 aal-fiscaal nummer
- 사회적-회계 번호
- sofi
- sofinummer
- identificatienummer
- identiteitsnummer
- 고유 id 번호
- 고유 id 번호
- uniqueidentityno #

## <a name="netherlands-drivers-license-number"></a>네덜란드 운전 면허 번호
이 중요 한 정보 유형 엔터티는 EU 드라이버의 라이선스 번호 중요 정보 유형 에서만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백과 구분 기호가 없는 10 자리 숫자
  
### <a name="pattern"></a>패턴

10자리 숫자
  
### <a name="checksum"></a>제외

아니요
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 정규식이 해당  `Regex_netherlands_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_netherlands_eu_driver's_license_number` 찾았습니다. 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

**Keywords_netherlands_eu_driver ' s_license_number**

- dl #
- driver license
- 드라이버 라이선스 번호
- 드라이버 라이선스
- drivers lic
- drivers license
- drivers licence
- driver's license
- 운전 면허 번호
- 운전 라이선스 번호
- 운전 면허 번호
- dlno #
- permis de conduire
- rijbewijs
- rijbewijsnummer

## <a name="netherlands-national-identification-number"></a>네덜란드 국가 식별 번호
이 중요 한 정보 유형 엔터티는 EU 국가 식별 번호 중요 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백이 나 구분 기호가 없는 9 자리 숫자
  
### <a name="pattern"></a>패턴

9자리 숫자
  
### <a name="checksum"></a>제외

예
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
  
- 이 함수는 해당  `Func_netherlands_eu_national_id_card` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를 찾았습니다.
    
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 이 함수는 해당  `Func_netherlands_eu_national_id_card` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
```xml
 <!--Netherland national identification number  -->
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_national_id_card" />
          <Match idRef="Keywords_netherlands_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_netherlands_eu_national_id_card"></a>Keywords_netherlands_eu_national_id_card

- bsn #
- bsn
- burgerservicenummer
- 시민 서비스 번호
- 사용자 번호
- 개인 번호
- 개인 숫자 코드
- 사용자 관련 번호
- persoonlijk nummer
- persoonlijke 코드
- persoonsgebonden
- persoonsnummer
- 사회 aal-fiscaal nummer
- 사회적-회계 번호
- sofi
- sofinummer
- identificatienummer
- identiteitsnummer
- 고유 id 번호
- 고유 id 번호
- uniqueidentityno #

## <a name="netherlands-passport-number"></a>네덜란드 여권 번호
이 중요 한 정보 유형 엔터티는 EU (유럽 여권 번호) 중요 한 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백이 나 구분 기호가 없는 9 개의 문자 또는 숫자
  
### <a name="pattern"></a>패턴

9 개의 문자 또는 숫자
  
### <a name="checksum"></a>제외

해당 사항 없음
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 정규식이 해당  `Regex_netherlands_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_netherlands_eu_passport_number` 찾았습니다. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

**Keywords_netherlands_eu_passport_number**

- 네덜란드어 여권 번호
- passport number
- 네덜란드 여권 번호
- nederlanden, nummer ort
- 고 대/ort
- nederlanden paspoortnummer
- paspoortnummer

## <a name="netherlands-tax-identification-number"></a>네덜란드 세금 식별 번호
이 중요 한 정보 유형 엔터티는 EU 세금 식별 번호로 중요 한 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백이 나 구분 기호가 없는 9 자리 숫자
  
### <a name="pattern"></a>패턴

9자리 숫자 
  
### <a name="checksum"></a>제외

예
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
  
- 이 함수는 해당  `Func_netherlands_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_netherlands_eu_tax_file_number` 찾았습니다. 
    
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 이 함수는 해당  `Func_netherlands_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
          <Match idRef="Keywords_netherlands_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_netherlands_eu_tax_file_number"></a>Keywords_netherlands_eu_tax_file_number

- btw nummer
- hollânske 세금 식별
- hulandes impuesto id 번호
- hulandes impuesto 식별
- identificatienummer belasting
- identificatienummer van belasting
- impuesto id 번호
- impuesto 번호
- nederlands belasting id nummer
- nederlands belasting identificatie
- nederlands belasting identificatienummer
- nederlands belastingnummer
- nederlandse belasting identificatie
- 네덜란드 세금 식별
- netherland의 세금 식별
- 네덜란드 언급
- netherland의 언급
- tax id

- 세금 식별 아니요
- 세금 식별 번호
- 세금 확인 tal
- 세금 없음 #
- 세금 없음
- 세금 번호
- 세금 등록 번호
- 세금 tal
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- 언급 id
- 언급 아니요
- 언급 #

## <a name="new-zealand-ministry-of-health-number"></a>뉴질랜드 보건부 (생명 번호)

### <a name="format"></a>형식일

3개 문자, 공백 1개(선택 사항) 및 4자리 숫자

### <a name="pattern"></a>패턴

3 개의 문자 (대/소문자 구분 안 함) 공백 (선택 사항) 4 자리 숫자

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_new_zealand_ministry_of_health_number 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_nz_terms의 키워드가 발견되었습니다.
- 체크섬이 통과됩니다.

```xml
<!-- New Zealand Health Number -->
<Entity id="2b71c1c8-d14e-4430-82dc-fd1ed6bf05c7" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_new_zealand_ministry_of_health_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_nz_terms" />
        </Any>
    </Pattern>
</Entity>
```

키워드

Keyword_nz_terms

- NHI 
- New Zealand 
- 상태 
- 처리가 
   
## <a name="norway-identification-number"></a>노르웨이 식별 번호

### <a name="format"></a>형식일

11자리 숫자

### <a name="pattern"></a>패턴

11자리 숫자:
- 생년월일에 해당하는 DDMMYY 형식의 6자리 숫자  
- 3자리 개인 번호  
- 2개의 검사 숫자

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_norway_id_number 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keyword_norway_id_number에서 키워드가 발견 되었습니다.
- 체크섬이 통과됩니다.
- DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Func_norway_id_numbe 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- 체크섬이 통과됩니다.

```xml
<!-- Norway Identification Number -->
<Entity id="d4c8a798-e9f2-4bd3-9652-500d24080fc3" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_norway_id_number"/>
     <Match idRef="Keyword_norway_id_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_norway_id_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_norway_id_number"></a>Keyword_norway_id_number

- Personal identification number
- Norwegian ID Number
- ID Number
- 확인과
- Personnummer
- Fødselsnummer

   
## <a name="philippines-unified-multi-purpose-identification-number"></a>필리핀 통합 다목적 식별 번호

### <a name="format"></a>형식일

하이픈으로 구분된 12자리 숫자

### <a name="pattern"></a>패턴

12자리 숫자:
- 4자리 숫자 
- 하이픈 
- 7자리 숫자 
- 하이픈 
- 1자리 숫자

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- 정규식 Regex_philippines_unified_id 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keyword_philippines_id에서 키워드가 발견 되었습니다.

```xml
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드
   
#### <a name="keyword_philippines_id"></a>Keyword_philippines_id

- Unified Multi-Purpose ID 
- UMID 
- Identity Card 
- Pinag-isang Multi-Layunin ID

## <a name="poland-drivers-license-number"></a>폴란드 운전 면허 번호
이 중요 한 정보 유형 엔터티는 EU 드라이버의 라이선스 번호 중요 정보 유형 에서만 사용할 수 있습니다.

### <a name="format"></a>형식일

두 개의 슬래시를 포함 하는 14 자리 숫자
  
### <a name="pattern"></a>패턴

14 자리 숫자와 2 개의 슬래시:
  
-  5자리 숫자 
- 정방향 슬래시
- 2자리 숫자
- 정방향 슬래시
- 7자리 숫자
    
### <a name="checksum"></a>제외

아니요
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 정규식이 해당  `Regex_poland_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_poland_eu_driver's_license_number` 찾았습니다. 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

**Keywords_poland_eu_driver ' s_license_number**

- dl #
- driver license
- 드라이버 라이선스 번호
- 드라이버 라이선스
- drivers lic
- drivers license
- drivers licence
- driver's license
- 운전 면허 번호
- 운전 라이선스 번호
- 운전 면허 번호
- dlno #
- prawo jazdy

## <a name="poland-identity-card"></a>폴란드 id 카드

### <a name="format"></a>형식일

3개의 문자 및 6자리 숫자

### <a name="pattern"></a>패턴

3개의 문자(대/소문자 구분 안 함)와 6자리 숫자

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 300 Func_polish_national_id 문자에 근접 한 경우에는이 유형의 중요 한 정보를 검색 하는 것으로 75% 확신 합니다.
Keyword_polish_national_id_passport_number의 키워드가 발견되었습니다.
체크섬이 통과됩니다.

```xml
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_polish_national_id_passport_number"></a>Keyword_polish_national_id_passport_number

- Dowód osobisty
- U r i dowodu osobistego
- Nazwa i u r i dowodu osobistego
- Nazwa i veiligheid dowodu osobistego
- Nazwa i nr dowodu tożsamości
- Dowód Tożsamości
- dow. 르.

   
## <a name="poland-national-id-pesel"></a>폴란드 국가 ID(PESEL)
이 중요 한 정보 유형 엔터티는 EU 국가 식별 번호 중요 한 정보 유형에 포함 되며 독립 실행형 중요 한 정보 유형 엔터티로 사용할 수 있습니다.

### <a name="format"></a>형식일

11자리 숫자

### <a name="pattern"></a>패턴

11자리 연속 숫자

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_pesel_identification_number 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_pesel_identification_number의 키워드가 발견되었습니다.
- 체크섬이 통과됩니다.

```xml
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_pesel_identification_number"></a>Keyword_pesel_identification_number

- dowód osobisty
- dowódosobisty
- niepowtarzalny u r i
- niepowtarzalnynumer
- veiligheid.-pesel
- veiligheid-pesel
- u r i identyfikacyjny
- pesel
- tożsamości narodowej

   
## <a name="poland-passport-number"></a>폴란드 여권 번호
이 중요 한 정보 유형 엔터티는 EU Passport 번호 중요 한 정보 형식에 포함 되며 독립 실행형 중요 한 정보 유형 엔터티로 사용할 수 있습니다.

### <a name="format"></a>형식일

2개 문자와 7자리 숫자

### <a name="pattern"></a>패턴

2개의 문자(대/소문자 구분 안 함)와 7자리 숫자

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_polish_passport_number 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_polish_national_id_passport_number의 키워드가 발견되었습니다.
- 체크섬이 통과됩니다.

```xml
<!-- Poland Passport Number -->
<Entity id="03937FB5-D2B6-4487-B61F-0F8BFF7C3517" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_passport_number" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
</Version>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_polish_national_id_passport_number"></a>Keyword_polish_national_id_passport_number

- U r i (zportu)
- Veiligheid. 고 zportu
- 고 zport

## <a name="poland-tax-identification-number"></a>폴란드 세금 식별 번호
이 중요 한 정보 유형 엔터티는 EU 세금 식별 번호로 중요 한 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백이 나 구분 기호가 없는 11 자리 숫자
  
### <a name="pattern"></a>패턴

11 자리 숫자
  
### <a name="checksum"></a>제외

예
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
  
- 이 함수는 해당  `Func_poland_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_poland_eu_tax_file_number` 찾았습니다. 
    
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 이 함수는 해당  `Func_poland_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
          <Match idRef="Keywords_poland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_poland_eu_tax_file_number"></a>Keywords_poland_eu_tax_file_number

nip #
- nip
- u r i identyfikacji podatkowej
- numeridentyfikacjipodatkowej #
- tax id

- 세금 식별 아니요
- 세금 식별 번호
- 세금 없음 #
- 세금 없음
- 세금 번호
- 세금 등록 번호
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- 언급 id
- 언급 아니요
- 언급 #
- vat id #
- vat id
- vat 아니요
- vat 번호
- vatid #
- vatid
- vatno #
   

## <a name="portugal-citizen-card-number"></a>포르투갈 시민 카드 번호
- 이 중요 한 정보 유형 엔터티는 EU 국가 식별 번호 중요 한 정보 유형에 포함 되며 독립 실행형 중요 한 정보 유형 엔터티로 사용할 수 있습니다.
- 이 중요 한 정보 유형 엔터티는 EU 주민 등록 번호 또는 해당 ID에 해당 하는 중요 한 정보 유형으로 포함 됩니다.


### <a name="format"></a>형식일

8자리 숫자

### <a name="pattern"></a>패턴

8자리 숫자

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- 정규식 Regex_portugal_citizen_card 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keyword_portugal_citizen_card에서 키워드가 발견 되었습니다.

```xml
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_portugal_citizen_card"></a>Keyword_portugal_citizen_card

- bilhete de identidade
- cartão de cidadão
- 시민 카드
- 문서 번호
- documento de identificação
- id 번호
- id 아니요
- identification number

- id 카드 번호 없음
- id 카드 번호
- 국가 id 카드
- nic
- número bi de 포르투갈
- número de identificação 민사
- número de identificação 회계
- número do documento
- 포르투갈 bi 번호


## <a name="portugal-drivers-license-number"></a>포르투갈 운전 면허 번호
이 중요 한 정보 유형 엔터티는 EU 드라이버의 라이선스 번호 중요 정보 유형 에서만 사용할 수 있습니다.

### <a name="format"></a>형식일

두 개의 문자와 지정 된 패턴에 있는 일곱 개의 숫자
  
### <a name="pattern"></a>패턴

두 문자 다음에 특수 문자를 사용한 7 개의 숫자를 입력 합니다.
  
- 2 개 문자 (대/소문자 구분 안 함) 
- 하이픈
- 6자리 숫자
- 공백
- 1자리 숫자
    
### <a name="checksum"></a>제외

아니요
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 정규식이 해당  `Regex_portugal_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_portugal_eu_driver's_license_number` 찾았습니다. 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

**Keywords_portugal_eu_driver ' s_license_number**

- dl #
- driver license
- 드라이버 라이선스 번호
- 드라이버 라이선스
- drivers lic
- drivers license
- drivers licence
- driver's license
- 운전 면허 번호
- 운전 라이선스 번호
- 운전 면허 번호
- dlno #
- carteira de motorista

## <a name="portugal-passport-number"></a>포르투갈 여권 번호
이 중요 한 정보 유형 엔터티는 EU (유럽 여권 번호) 중요 한 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백 또는 구분 기호가 없는 한 문자 다음에 6 자리 숫자
  
### <a name="pattern"></a>패턴

1 개의 문자 다음에 6 자리 숫자:
  
- 1개 문자(대/소문자 구분 안 함)
- 6자리 숫자
    
### <a name="checksum"></a>제외

아니요
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 정규식이 해당  `Regex_portugal_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_portugal_eu_passport_number` 찾았습니다. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

**Keywords_portugal_eu_passport_number**

여권 번호 포르투갈어 passport 번호 passport número do passaporte

## <a name="portugal-tax-identification-number"></a>포르투갈 세금 식별 번호
이 중요 한 정보 유형 엔터티는 EU 세금 식별 번호로 중요 한 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백이 나 구분 기호가 없는 9 자리 숫자
  
### <a name="pattern"></a>패턴

9자리 숫자
  
### <a name="checksum"></a>제외

예
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
  
- 이 함수는 해당  `Func_portugal_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_portugal_eu_tax_file_number` 찾았습니다. 
    
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 이 함수는 해당  `Func_portugal_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
          <Match idRef="Keywords_portugal_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_portugal_eu_tax_file_number"></a>Keywords_portugal_eu_tax_file_number

- cpf #
- cpf
- m #
- m
- número de identificação fisca
- numero 회계
- tax id

- 세금 식별 아니요
- 세금 식별 번호
- 세금 없음 #
- 세금 없음
- 세금 번호
- 세금 등록 번호
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- 언급 id
- 언급 아니요
- 언급 #


## <a name="romania-drivers-license-number"></a>루마니아 운전 면허 번호
이 중요 한 정보 유형 엔터티는 EU 드라이버의 라이선스 번호 중요 정보 유형 에서만 사용할 수 있습니다.

### <a name="format"></a>형식일

한 문자 다음에 8 자리 숫자
  
### <a name="pattern"></a>패턴

1 개의 문자 다음에 8 자리 숫자:
  
- 1 개 문자 (대/소문자 구분 안 함) 또는 숫자 
- 8자리 숫자
    
### <a name="checksum"></a>제외

아니요
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 정규식이 해당  `Regex_romania_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_romania_eu_driver's_license_number` 찾았습니다. 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

**Keywords_romania_eu_driver ' s_license_number**

- dl #
- driver license
- 드라이버 라이선스 번호
- 드라이버 라이선스
- drivers lic
- drivers license
- drivers licence
- driver's license
- 운전 면허 번호
- 운전 라이선스 번호
- 운전 면허 번호
- dlno #
- permis de conducere

## <a name="romania-national-identification-number"></a>루마니아 국가 식별 번호
이 중요 한 정보 유형 엔터티는 EU 국가 식별 번호 중요 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백과 구분 기호가 없는 13 자리 숫자
  
### <a name="pattern"></a>패턴

13자리 숫자
  
### <a name="checksum"></a>제외

예
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
  
- 이 함수는 해당  `Func_romania_eu_national_id_card` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_romania_eu_national_id_card` 찾았습니다. 
    
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 이 함수는 해당  `Func_romania_eu_national_id_card` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
```xml
 <!--Romania national identification number  -->
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
          <Match idRef="Keywords_romania_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_romania_eu_national_id_card"></a>Keywords_romania_eu_national_id_card

- cnp #
- cnp
- cod identificare personal
- cod 숫자 개인
- cod unic identificare
- codnumericpersonal #
- codul 회계 veiligheid
- identificarea fiscală veiligheid #
- id-ul taxei
- 보험 번호
- insurancenumber #
- 국가 id #
- 
national id
- 국가 식별 번호
- număr identificare personal
- număr identitate
- număr personal unic
- număridentitate #
- număridentitate
- numărpersonalunic #
- numărpersonalunic
- număru de identificare fiscală
- numărul de identificare fiscală
- 개인 숫자 코드
- pin #
- pin
- 세금 파일 번호
- 세금 파일 번호
- tax id

- 세금 식별 아니요
- 세금 식별 번호
- 세금 없음 #
- 세금 없음
- 세금 번호
- 세금 등록 번호
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- 언급 id
- 언급 아니요
- 언급 #
- 고유 id 번호
- 고유 id 번호
- uniqueidentityno #
- uniqueidentityno

## <a name="romania-passport-number"></a>루마니아 여권 번호
이 중요 한 정보 유형 엔터티는 EU (유럽 여권 번호) 중요 한 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백과 구분 기호를 사용 하지 않고 8 또는 9 자리 숫자
  
### <a name="pattern"></a>패턴

8 또는 9 자리 숫자
  
### <a name="checksum"></a>제외

아니요
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 정규식이 해당  `Regex_romania_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_romania_eu_passport_number` 찾았습니다. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

**Keywords_romania_eu_passport_number**

- passport number
- 루마니아어 여권 번호
- passport 아니요
- numărul pașaportului

## <a name="romania-tax-identification-number"></a>루마니아 세금 식별 번호
이 중요 한 정보 유형 엔터티는 EU 세금 식별 번호로 중요 한 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백이 나 구분 기호가 없는 13 자리 숫자
  
### <a name="pattern"></a>패턴

13자리 숫자
  
### <a name="checksum"></a>제외

해당 사항 없음
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 정규식이 해당  `Regex_romania_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_romania_eu_tax_file_number` 찾았습니다. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_romania_eu_tax_file_number"></a>Keywords_romania_eu_tax_file_number

- cnp #
- cnp
- cod identificare personal
- cod 숫자 개인
- cod unic identificare
- codnumericpersonal #
- codul 회계 veiligheid
- identificarea fiscală veiligheid #
- id-ul taxei
- 보험 번호
- insurancenumber #
- 국가 id #
- 
national id
- 국가 식별 번호
- număr identificare personal
- număr identitate
- număr personal unic
- număridentitate #
- număridentitate
- numărpersonalunic #
- numărpersonalunic
- număru de identificare fiscală
- numărul de identificare fiscală
- 개인 숫자 코드
- pin #
- pin
- 세금 파일 번호
- 세금 파일 번호
- tax id

- 세금 식별 아니요
- 세금 식별 번호
- 세금 없음 #
- 세금 없음
- 세금 번호
- 세금 등록 번호
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- 언급 id
- 언급 아니요
- 언급 #
- 고유 id 번호
- 고유 id 번호
- uniqueidentityno #
- uniqueidentityno



## <a name="saudi-arabia-national-id"></a>사우디 아라비아 국가 ID

### <a name="format"></a>형식일

10자리 숫자

### <a name="pattern"></a>패턴

10자리 연속 숫자

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Regex_saudi_arabia_national_id 정규식이 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_saudi_arabia_national_id의 키워드가 발견되었습니다.

```xml
<!-- Saudi Arabia National ID -->
<Entity id="8c5a0ba8-404a-41a3-8871-746aa21ee6c0" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_saudi_arabia_national_id" />
        <Any minMatches="1">
          <Match idRef="Keyword_saudi_arabia_national_id" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_saudi_arabia_national_id"></a>Keyword_saudi_arabia_national_id

- Identification Card 
- I card number 
- ID number 
- الوطنية الهوية بطاقة رقم 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a>싱가포르 NRIC (국가 등록 id 카드) 번호

### <a name="format"></a>형식일

9개의 문자 및 숫자

### <a name="pattern"></a>패턴

- 9개의 문자 및 숫자:
- 문자 "F", "G", "S" 또는 "T"(대/소문자 구분 안 함)  
- 7자리 숫자 
- 알파벳 검사 숫자

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- 정규식 Regex_singapore_nric 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keyword_singapore_nric에서 키워드가 발견 되었습니다.
- 체크섬이 통과됩니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- 정규식 Regex_singapore_nric 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- 체크섬이 통과됩니다.

```xml
<!-- Singapore National Registration Identity Card (NRIC) Number -->
<Entity id="cead390a-dd83-4856-9751-fb6dc98c34da" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_singapore_nric"/>
     <Match idRef="Keyword_singapore_nric"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_singapore_nric"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드
   
#### <a name="keyword_singapore_nric"></a>Keyword_singapore_nric

- National Registration Identity Card 
- Identity Card Number 
- NRIC 
- 비용 
- Foreign Identification Number 
- 삭제할 
- 身份证 
- 身份證 

## <a name="slovakia-drivers-license-number"></a>슬로바키아 운전 면허 번호
이 중요 한 정보 유형 엔터티는 EU 드라이버의 라이선스 번호 중요 정보 유형 에서만 사용할 수 있습니다.

### <a name="format"></a>형식일

한 문자 다음에 7 자리 숫자
  
### <a name="pattern"></a>패턴

한 문자 다음에 7 자리 숫자
  
- 1 개 문자 (대/소문자 구분 안 함) 또는 숫자
-  7자리 숫자 
    
### <a name="checksum"></a>제외

아니요
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 정규식이 해당  `Regex_slovakia_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_slovakia_eu_driver's_license_number` 찾았습니다. 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

**Keywords_slovakia_eu_driver ' s_license_number**

dl # driver license driver 면허 번호 드라이버 라이선스 드라이버 lic
drivers license driver 면허 드라이버의 라이선스 드라이버 라이선스 번호 운전 면허 번호 라이센스 번호 제어 # vodičský preukaz

## <a name="slovakia-national-identification-number"></a>슬로바키아 국가 식별 번호
이 중요 한 정보 유형 엔터티는 EU 국가 식별 번호 중요 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

백슬래시 하나를 포함 하는 10 자리 숫자
  
### <a name="pattern"></a>패턴

백슬래시 하나를 포함 하는 10 자리 숫자:
  
### <a name="checksum"></a>제외

예
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
  
- 이 함수는 해당  `Func_slovakia_eu_national_id_card` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_slovakia_eu_national_id_card` 찾았습니다. 
    
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 이 함수는 해당  `Func_slovakia_eu_national_id_card` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
```xml
 <!-- Slovakia national identification number -->
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
          <Match idRef="Keywords_slovakia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_slovakia_eu_national_id_card"></a>Keywords_slovakia_eu_national_id_card

- azonosító szám
- 돌 번호
- číslo národnej identifikačnej karty
- číslo občianského preukazu
- daňové číslo
- id 번호
- id 아니요
- identification number

- identifikačná karta č
- identifikačné číslo
- id 카드 번호 없음
- id 카드 번호
- národná identifikačná značka č
- 국가 번호
- nationalnumber #
- nemzeti személyazonosító igazolvány
- personalidnumber #
- rč
- rodne cislo
- rodné číslo
- social security number

- ssn #
- ssn
- személyi igazolvány szám
- személyi igazolvány száma
- személyigazolvány szám
- 세금 파일 번호
- 세금 파일 번호
- tax id

- 세금 식별 아니요
- 세금 식별 번호
- 세금 없음 #
- 세금 없음
- 세금 번호
- 세금 등록 번호
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- 언급 id
- 언급 아니요
- 언급 #

## <a name="slovakia-passport-number"></a>슬로바키아 여권 번호
이 중요 한 정보 유형 엔터티는 EU (유럽 여권 번호) 중요 한 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백 또는 구분 기호가 없는 한 자리 숫자 또는 문자 다음에 일곱 자리 숫자
  
### <a name="pattern"></a>패턴

1 자리 숫자 또는 문자 (대/소문자 구분 안 함)와 7 자리 숫자
  
### <a name="checksum"></a>제외

아니요
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 정규식이 해당  `Regex_slovakia_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_slovakia_eu_passport_number` 찾았습니다. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

**Keywords_slovakia_eu_passport_number**

- passport number
- 슬로바키아어 여권 번호
- passport 아니요
- číslo (u)

## <a name="slovakia-tax-identification-number"></a>슬로바키아 세금 식별 번호
이 중요 한 정보 유형 엔터티는 EU 세금 식별 번호로 중요 한 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백이 나 구분 기호가 없는 10 자리 숫자
  
### <a name="pattern"></a>패턴

10자리 숫자
  
### <a name="checksum"></a>제외

해당 사항 없음
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 정규식이 해당  `Regex_slovakia_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_slovakia_eu_tax_file_number` 찾았습니다. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_slovakia_eu_tax_file_number"></a>Keywords_slovakia_eu_tax_file_number

- azonosító szám
- 돌 번호
- číslo národnej identifikačnej karty
- číslo občianského preukazu
- daňové číslo
- id 번호
- id 아니요
- identification number

- identifikačná karta č
- identifikačné číslo
- id 카드 번호 없음
- id 카드 번호
- národná identifikačná značka č
- 국가 번호
- nationalnumber #
- nemzeti személyazonosító igazolvány
- personalidnumber #
- rč
- rodne cislo
- rodné číslo
- social security number

- ssn #
- ssn
- személyi igazolvány szám
- személyi igazolvány száma
- személyigazolvány szám
- 세금 파일 번호
- 세금 파일 번호
- tax id

- 세금 식별 아니요
- 세금 식별 번호
- 세금 없음 #
- 세금 없음
- 세금 번호
- 세금 등록 번호
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- 언급 id
- 언급 아니요
- 언급 #


## <a name="slovenia-drivers-license-number"></a>슬로베니아 운전 면허 번호
이 중요 한 정보 유형 엔터티는 EU 드라이버의 라이선스 번호 중요 정보 유형 에서만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백과 구분 기호를 사용 하지 않고 9 자리 숫자
  
### <a name="pattern"></a>패턴

9자리 숫자
  
### <a name="checksum"></a>제외

아니요
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 정규식이 해당  `Regex_slovenia_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_slovenia_eu_driver's_license_number` 찾았습니다. 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

**Keywords_slovenia_eu_driver ' s_license_number**

- dl #
- driver license
- 드라이버 라이선스 번호
- 드라이버 라이선스
- drivers lic
- drivers license
- drivers licence
- driver's license 
- 운전 면허 번호
- 운전 라이선스 번호
- 운전 면허 번호
- dlno #
- vozniško dovoljenje

## <a name="slovenia-national-identification-number"></a>슬로베니아 국가 식별 번호
이 중요 한 정보 유형 엔터티는 EU 국가 식별 번호 중요 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백이 나 구분 기호가 없는 13 자리 숫자
  
### <a name="pattern"></a>패턴

지정 된 패턴의 13 자리 숫자:
  
-  생년월일 (DDMMLLL)에 해당 하는 7 자리 숫자 이며 "LLL"은 출생 연도의 마지막 세 자리에 해당 합니다. 
- 출생 면적에 해당 하는 2 자리 숫자
- 같은 날에 태어난 사용자의 성별 및 일련 번호 조합에 해당 하는 3 자리 숫자 (남성는 000-499, 암은 500-999)
- 검사 숫자 1 개
    
### <a name="checksum"></a>제외

예
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
  
- 이 함수는 해당  `Func_slovenia_eu_national_id_card` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_slovenia_eu_national_id_card` 찾았습니다. 
    
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 이 함수는 해당  `Func_slovenia_eu_national_id_card` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
```xml
 <!-- Slovenia national identification number -->
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
          <Match idRef="Keywords_slovenia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_slovenia_eu_national_id_card"></a>Keywords_slovenia_eu_national_id_card

- ed명령이 vena številka glavnega državljana
- emšo
- enotna maticna številka obcana
- id 카드
- identification number

- identifikacijska številka
- id 카드
- nac사서함 alna id
- nacpotni alni 목록
- 
national id
- osebna izkaznica
- osebni koda
- osebni ne
- osebni številka
- 개인 코드
- 개인 번호
- 개인 숫자 코드
- številka državljana
- 고유한 시민 번호
- 고유 id 번호
- 고유 id 번호
- 고유 마스터 시민 번호
- 고유 등록 번호
- uniqueidentityno #
- uniqueidentityno #

## <a name="slovenia-passport-number"></a>슬로베니아 여권 번호
이 중요 한 정보 유형 엔터티는 EU (유럽 여권 번호) 중요 한 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백 또는 구분 기호가 없는 7 자리, 두 문자
  
### <a name="pattern"></a>패턴

2 개 문자와 7 자리 숫자를 입력 합니다.
  
- "P" 문자
- 대문자 1 개
- 7자리 숫자
    
### <a name="checksum"></a>제외

아니요
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 정규식이 해당  `Regex_slovenia_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_slovenia_eu_passport_number` 찾았습니다. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

**Keywords_slovenia_eu_passport_number**

여권 번호 슬로베니아어 여권 번호 passport no številka potnega lista

## <a name="slovenia-tax-identification-number"></a>슬로베니아 세금 식별 번호
이 중요 한 정보 유형 엔터티는 EU 세금 식별 번호로 중요 한 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백이 나 구분 기호가 없는 8 자리 숫자
  
### <a name="pattern"></a>패턴

8자리 숫자
  
### <a name="checksum"></a>제외

예
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
  
- 이 함수는 해당  `Func_slovenia_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_slovenia_eu_tax_file_number` 찾았습니다. 
    
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 이 함수는 해당  `Func_slovenia_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_nation_eu_tax_file_number" />
          <Match idRef="Keywords_nation_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_slovenia_eu_tax_file_number"></a>Keywords_slovenia_eu_tax_file_number

- davčna številka
- identifikacijska številka davka
- številka davčne datoteke
- 세금 파일 번호
- 세금 파일 번호
- tax id

- 세금 식별 아니요
- 세금 식별 번호
- 세금 없음 #
- 세금 없음
- 세금 번호
- 세금 등록 번호
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- 언급 id
- 언급 아니요
- 언급 #



## <a name="south-africa-identification-number"></a>남아프리카 공화국 식별 번호

### <a name="format"></a>형식일

공백을 포함할 수 있는 13자리 숫자

### <a name="pattern"></a>패턴

13자리 숫자:
- 생년월일에 해당하는 YYMMDD 형식의 6자리 숫자  
- 4자리 숫자 
- 1자리 시민권 표시  
- 숫자 "8" 또는 "9"  
- 체크섬 숫자에 해당하는 1자리 숫자

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_south_africa_identification_number 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keyword_south_africa_identification_number에서 키워드가 발견 되었습니다.
- 체크섬이 통과됩니다.

```xml
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드
   
#### <a name="keyword_south_africa_identification_number"></a>Keyword_south_africa_identification_number

- Identity card
- ID
- 확인과 
   
## <a name="south-korea-resident-registration-number"></a>대한민국 등록 번호

### <a name="format"></a>형식일

하이픈을 포함하는 13자리 숫자

### <a name="pattern"></a>패턴

13자리 숫자:
- 생년월일에 해당하는 YYMMDD 형식의 6자리 숫자  
- 하이픈 
- 세기 및 성별에 따라 결정되는 1자리 숫자  
- 4자리 출생 지역 코드  
- 앞 번호가 동일한 사람을 구분하기 위해 사용되는 1자리 숫자  
- 검사 숫자

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_south_korea_resident_number 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keyword_south_korea_resident_number에서 키워드가 발견 되었습니다.
- 체크섬이 통과됩니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Func_south_korea_resident_number 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- 체크섬이 통과됩니다.

```xml
<!-- South Korea Resident Registration Number -->
<Entity id="5b802e18-ba80-44c4-bc83-bf2ad36ae36a" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_korea_resident_number"/>
     <Match idRef="Keyword_south_korea_resident_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_south_korea_resident_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드
   
#### <a name="keyword_south_korea_resident_number"></a>Keyword_south_korea_resident_number

- National ID card 
- Citizen's Registration Number 
- Jumin deungnok beonho 
- RRN 
- 주민등록번호

## <a name="spain-drivers-license-number"></a>스페인 운전 면허 번호
이 중요 한 정보 유형 엔터티는 EU 드라이버의 라이선스 번호 중요 정보 유형 에서만 사용할 수 있습니다.

### <a name="format"></a>형식일

8 자리 숫자와 문자 1 개
  
### <a name="pattern"></a>패턴

8 자리 숫자와 문자 1 개:
  
- 8자리 숫자 
- 1 자리 숫자 또는 문자 (대/소문자 구분 안 함)
    
### <a name="checksum"></a>제외

예
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 이 함수는 해당  `Func_spain_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_spain_eu_driver's_license_number` 찾았습니다. 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

**Keywords_spain_eu_driver ' s_license_number**

- dlno #
- dl #
- drivers lic
- 드라이버 라이선스
- driver license
- drivers licence
- drivers license
- driver's licence
- driver's license
- driving licence
- driving license
- 드라이버 라이선스 번호
- 드라이버 라이선스 번호
- 영향 요소 라이선스 번호
- 운전 면허 번호
- 운전 라이선스 번호
- 운전 면허 번호
- 운전 라이선스 번호
- 운전 면허 번호
- 추진 허용
- 제어 허용 번호
- permiso de conducción
- permiso conducción
- número licencia conducir
- número de 네트워크 de conducir
- número carnet conducir
- licencia conducir
- número de permiso de conducir
- número de permiso conducir
- número permiso conducir
- permiso conducir
- licencia de manejo
- el carnet de conducir
- carnet conducir

## <a name="spain-national-identification-number"></a>스페인 국립 식별 번호
이 중요 한 정보 유형 엔터티는 EU 국가 식별 번호 중요 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

7 자리 숫자와 문자 1 개
  
### <a name="pattern"></a>패턴

7 자리 숫자와 문자 1 개
  
- 7자리 숫자
- 1 자리 숫자 또는 문자 (대/소문자 구분 안 함)
    
### <a name="checksum"></a>제외

해당 사항 없음
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 정규식이 해당  `Regex_spain_eu_national_id_card` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_spain_eu_national_id_card"` 찾았습니다. 
    
```xml
<!-- Spain national identification number -->
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_national_id_card" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_spain_eu_national_id_card"></a>Keywords_spain_eu_national_id_card

- carné de identidad
- dni #
- dni
- dninúmero #
- documento nacional de identidad
- identidad único
- identidadúnico #
- 보험 번호
- 국가 식별 번호
- 국가 id
- nationalid #
- nationalidno #
- nie #
- nie
- nienúmero #
- número de identificación
- número nacional identidad
- 개인 식별 번호
- 개인 id 없음
- 고유 id 번호
- uniqueid #

## <a name="spain-passport-number"></a>스페인 여권 번호
이 중요 한 정보 유형 엔터티는 EU (유럽 여권 번호) 중요 한 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백이 나 구분 기호가 없는 문자 및 숫자의 8 자리 또는 9 자 조합
  
### <a name="pattern"></a>패턴

문자와 숫자의 8 자리 또는 9 자리 조합:
  
-  두 자리 숫자 또는 문자 
- 1 자리 숫자 또는 문자 (선택 사항)
- 6자리 숫자
    
### <a name="checksum"></a>제외

해당 사항 없음
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 정규식이 해당  `Regex_spain_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_spain_eu_passport_number` 찾았습니다. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

**Keywords_spain_eu_passport_number**

- 여권
- 스페인 여권
- passport 책
- passport number
- passport 아니요
- pasaporte
- número pasaporte
- españa pasaporte
- pasaporte


## <a name="spain-social-security-number-ssn"></a>스페인 SSN (사회 보장 번호)
이 중요 한 정보 유형 엔터티는 EU 주민 등록 번호 또는 동등한 ID 중요 정보 유형에 포함 되며 독립 실행형 중요 한 정보 유형 엔터티로 사용할 수 있습니다.

### <a name="format"></a>형식일

11-12자리 숫자

### <a name="pattern"></a>패턴

11-12 자리 숫자:
- 2자리 숫자 
- 정방향 슬래시 1개(선택 사항) 
- 7-8자리 숫자 
- 정방향 슬래시 1개(선택 사항) 
- 2자리 숫자

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_spanish_social_security_number 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- 체크섬이 통과됩니다.

```xml
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

없음

## <a name="spain-tax-identification-number"></a>스페인 세금 식별 번호
이 중요 한 정보 유형 엔터티는 EU 세금 식별 번호로 중요 한 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

지정 된 패턴에 7 ~ 8 자리 숫자와 한 가지 또는 두 개의 문자가 있습니다.
  
### <a name="pattern"></a>패턴

스페인 국내 Id 카드가 있는 스페인어 (자연 사용자):
  
-  8자리 숫자 
- 대문자 1 개 (대/소문자 구분) 
    
스페인 국가 Id 카드가 없는 상주 하지 않는 Spaniards
  
- 1 개의 대문자 "L" (대/소문자 구분)
- 7자리 숫자
- 대문자 1 개 (대/소문자 구분) 
    
스페인 국가 Id 카드를 사용 하지 않고 14 년 동안 상주 하는 Spaniards:
  
- 1 개의 대문자 "K" (대/소문자 구분)
-  7자리 숫자 
- 대문자 1 개 (대/소문자 구분)
    
Foreigner의 식별 번호를 사용 하는 Foreigners
  
- "X", "Y" 또는 "Z" (대/소문자 구분)의 대문자 1 개 
- 7자리 숫자
- 대문자 1 개 (대/소문자 구분) 
    
Foreigner의 Id 번호가 없는 Foreigners
  
- "M"을 나타내는 대문자 1 개 (대/소문자 구분) 
- 7자리 숫자
- 대문자 1 개 (대/소문자 구분) 
    
### <a name="checksum"></a>제외

예
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
  
- 이 함수는 해당  `Func_spain_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_spain_eu_tax_file_number` 찾았습니다. 
    
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 이 함수는 해당  `Func_spain_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_spain_eu_tax_file_number"></a>Keywords_spain_eu_tax_file_number

- cif
- cifid #
- cifnúmero #
- número de contribuyente
- número de identificación 회계
- número de impuesto corporativo
- spanishcifid #
- spanishcifid
- spanishcifno #
- spanishcifno
- 세금 파일 번호
- 세금 파일 번호
- tax id

- 세금 식별 아니요
- 세금 식별 번호
- 세금 없음 #
- 세금 없음
- 세금 번호
- 세금 등록 번호
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- 언급 id
- 언급 아니요
- 언급 #


## <a name="sql-server-connection-string"></a>SQL Server 연결 문자열

### <a name="format"></a>형식일

아래 패턴에 설명 된 문자 및 문자열이 뒤에 오는 "User Id", "User ID", "uid" 또는 "UserId"입니다.

### <a name="pattern"></a>패턴

- 문자열 "User Id", "User ID", "uid" 또는 "UserId"
- 1-200에서 대/소문자, 숫자, 기호, 특수 문자 또는 공백 사이의 조합
- 문자열 "Password" 또는 "pwd" (여기에서 "pwd" 앞에 소문자 문자가 오지 않음)
- 등호 (=)
- 달러 기호 ($), 백분율 기호 (%, 부등호 (>), 기호 (@), 따옴표 ("), 세미콜론 (;), 왼쪽 중괄호 ([) 또는 왼쪽 대괄호 ({))가 아닌 모든 문자
- 세미콜론 (;), 슬래시 (/) 또는 따옴표 (")가 아닌 7-128 문자의 조합
- 세미콜론 (;) 또는 따옴표 (")

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- 정규식 CEP_Regex_SQLServerConnectionString 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- CEP_GlobalFilter의 키워드를 찾을 수 **없습니다** .
- 정규식 CEP_PasswordPlaceHolder에서 해당 패턴과 일치 하는 콘텐츠 **를 찾지 않습니다** .
- 정규식 CEP_CommonExampleKeywords에서 해당 패턴과 일치 하는 콘텐츠 **를 찾지 않습니다** .

```sql
<!---SQL Server Connection String>
<Entity id="e76b6205-d3cb-46f2-bd63-c90153f2f97d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_SQLServerConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_GlobalFilter" />
            <Match idRef="CEP_PasswordPlaceHolder" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="cep_globalfilter"></a>CEP_GlobalFilter

- 일부 암호
- somepassword
- secretPassword
- 예

#### <a name="cep_passwordplaceholder"></a>CEP_PasswordPlaceHolder

기술적으로이 중요 한 정보 유형은 키워드 목록이 아니라 정규식을 사용 하 여 이러한 키워드를 식별 합니다.

- 암호나 pwd에 0-2 공백, 등호 (=), 0-2 공백 및 별표 (*)-----------------------
- 암호나 pwd 뒤에 다음이 있습니다.
    - 등호 (=)
    - 보다 작음 기호 (<)
    - 대문자나 소문자, digits, 별표 (*), 하이픈 (-), 밑줄 (_) 또는 공백 문자인 1-200 문자의 조합
    - 보다 큼 기호 (>)

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

기술적으로이 중요 한 정보 유형은 키워드 목록이 아니라 정규식을 사용 하 여 이러한 키워드를 식별 합니다.

- 극동
- fabrikam
- 대양
- 샌드박스
- 용 onebox
- 로컬
- 127.0.0.1
- testacs입니다.<!--no-hyperlink-->ccw
- s-int<!--no-hyperlink-->투자

## <a name="sweden-drivers-license-number"></a>스웨덴 운전 면허 번호
이 중요 한 정보 유형 엔터티는 EU 드라이버의 라이선스 번호 중요 정보 유형 에서만 사용할 수 있습니다.

### <a name="format"></a>형식일

하이픈을 포함 하는 10 자리 숫자
  
### <a name="pattern"></a>패턴

하이픈을 포함 하는 10 자리 숫자:
  
-  6자리 숫자 
- 하이픈
- 4자리 숫자
    
### <a name="checksum"></a>제외

아니요
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 정규식이 해당  `Regex_sweden_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_sweden_eu_driver's_license_number` 찾았습니다. 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a>키워드

**Keywords_sweden_eu_driver ' s_license_number**

- dl #
- driver license
- 드라이버 라이선스 번호
- 드라이버 라이선스
- drivers lic
- drivers license
- drivers licence
- driver's license
- 운전 면허 번호
- 운전 라이선스 번호
- 운전 면허 번호
- dlno #
- körkort

## <a name="sweden-national-id"></a>스웨덴 국가 ID
이 중요 한 정보 유형 엔터티는 EU 국가 식별 번호 중요 한 정보 유형에 포함 되며 독립 실행형 중요 한 정보 유형 엔터티로 사용할 수 있습니다.

### <a name="format"></a>형식일

10 또는 12자리 숫자와 선택적 구분 기호

### <a name="pattern"></a>패턴

10 또는 12자리 숫자와 선택적 구분 기호:
- 2-4자리 숫자(선택 사항) 
- YYMMDD 날짜 형식의 6자리 숫자 
- 구분 기호 "-" 또는 "+"(선택 사항) 및
- 4자리 숫자

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_swedish_national_identifier 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- 체크섬이 통과됩니다.

```xml
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

아니요
   
## <a name="sweden-passport-number"></a>스웨덴 여권 번호
이 중요 한 정보 유형 엔터티는 EU Passport 번호 중요 한 정보 형식에 포함 되며 독립 실행형 중요 한 정보 유형 엔터티로 사용할 수 있습니다.

### <a name="format"></a>형식일

8자리 숫자

### <a name="pattern"></a>패턴

8자리 연속 숫자

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Regex_sweden_passport_number 정규식이 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- 다음 중 하나가 충족됩니다.
    - Keyword_passport의 키워드가 발견되었습니다.
    - Keyword_sweden_passport의 키워드가 발견되었습니다.

```xml
<!-- Sweden Passport Number -->
<Entity id="ba4e7456-55a9-4d89-9140-c33673553526" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_sweden_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_passport" />
          <Match idRef="Keyword_sweden_passport" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드
   
#### <a name="keyword_sweden_passport"></a>Keyword_sweden_passport

- visa requirements 
- Alien Registration Card 
- Schengen visas 
- Schengen visa 
- Visa Processing 
- Visa Type 
- Single Entry 
- Multiple Entry 
- G3 Processing Fees 

#### <a name="keyword_passport"></a>Keyword_passport

- Passport Number 
- Passport No 
- Passport # 
- 여권 # 
- PassportID 
- Passportno 
- passportnumber 
- パスポート 
- パスポート番号 
- パスポートのNum 
- パスポート＃ 
- Numéro de passeport 
- Passeport n ° 
- Passeport Non 
- Passeport # 
- 포트 # 
- 지/포트 아님 
- Passeportn ° 

## <a name="sweden-social-security-number-or-equivalent-identification"></a>스웨덴 주민 등록 번호 또는 이와 동등한 정보
이 중요 한 정보 유형 엔터티는 EU 주민 등록 번호 또는 해당 ID 중요 정보 유형에 서만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백과 구분 기호를 사용 하지 않고 12 자리 숫자
  
### <a name="pattern"></a>패턴

12자리 숫자:
  
-  출생 날짜에 해당 하는 8 자리 숫자 (YYYYMMDD) 
- 일련 번호에 해당 하는 3 자리 숫자: 
  - 일련 번호의 마지막 숫자는 남성에 홀수를 할당 하는 성별과 암의 짝수를 나타냅니다.
  - 최대 1990의 일련 번호를 사용 하 여 전화를 corresponded 하는 국가 (1947 이전 1947에는 immigrants 앞에 탄생 한 경우)에는 세금 기록에 따라 해당 번호에 대 한 특수 코드 (일반적으로 9 자리 숫자)가 포함 되어 있습니다. 
- 검사 숫자 1 개
    
### <a name="checksum"></a>제외

예
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
  
- 이 함수는 해당  `Func_sweden_eu_ssn_or_equivalent` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_sweden_eu_ssn_or_equivalent` 찾았습니다. 
    
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 이 함수는 해당  `Func_sweden_eu_ssn_or_equivalent` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_sweden_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_sweden_eu_ssn_or_equivalent"></a>Keywords_sweden_eu_ssn_or_equivalent

- 개인 id 번호
- identification number
- 개인 id 없음
- identity no
- id 아니요
- 개인 식별 아니요
- personnummer id
- personligt id-nummer
- unikt id-nummer
- personnummer
- identifikationsnumret
- personnummer #
- identifikationsnumret #

## <a name="sweden-tax-identification-number"></a>스웨덴 세금 식별 번호
이 중요 한 정보 유형 엔터티는 EU 세금 식별 번호로 중요 한 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

지정 된 패턴의 10 자리 숫자와 기호
  
### <a name="pattern"></a>패턴

10 자리 숫자와 기호:
  
- 생년월일에 해당 하는 6 자리 숫자 (YYMMDD) 
- 더하기 기호, 빼기 기호 또는 백슬래시
- 다음은 식별 번호를 고유 하 게 만드는 3 자리 숫자입니다. 
  - 1990 이전에 실행 된 번호의 경우 일곱째 및 여덟 번째 숫자는 출생 또는 외부에서 태어난 사람의 국가를 식별 합니다.
  - 아홉 번째 위치의 숫자는 성별에 대 한 홀수 또는 암도를 나타냅니다.
- 검사 숫자 1 개
    
### <a name="checksum"></a>제외

예
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
  
- 이 함수는 해당  `Func_sweden_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_sweden_eu_tax_file_number` 찾았습니다. 
    
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 이 함수는 해당  `Func_sweden_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
          <Match idRef="Keywords_sweden_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_sweden_eu_tax_file_number"></a>Keywords_sweden_eu_tax_file_number

- 개인 id 번호
- personnummer
- (nummer at&t id)
- identifikation at&t
- skattebetalarens identifikationsnummer
- sverige 언급
- 세금 파일
- tax id

- 세금 식별 아니요
- 세금 식별 번호
- 세금 없음 #
- 세금 없음
- 세금 번호
- 세금 등록 번호
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- 언급 id
- 언급 아니요
- 언급 #



## <a name="swift-code"></a>SWIFT 코드

### <a name="format"></a>형식일

4개의 문자, 5-31개 문자 또는 숫자

### <a name="pattern"></a>패턴

4개의 문자, 5-31개 문자 또는 숫자:
- 4문자 은행 코드(대/소문자 구분 안 함) 
- 선택적 공백 1개 
- 4-28개 문자 또는 숫자[BBAN(기본 은행 계좌 번호)] 
- 선택적 공백 1개 
- 1-3개 문자 또는 숫자(BBAN의 나머지)

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Regex_swift 정규식이 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_swift의 키워드가 발견되었습니다.

```xml
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드
   
#### <a name="keyword_swift"></a>Keyword_swift

- international organization for standardization 9362 
- iso 9362 
- iso9362 
- swift\# 
- swiftcode 
- swiftnumber 
- swiftroutingnumber 
- swift code 
- swift number # 
- swift routing number 
- bic number 
- bic code 
- bic \# 
- bic\# 
- bank identifier code 
- 標準化 9362 
- 迅速＃ 
- SWIFTコード 
- SWIFT番号 
- 迅速なルーティング番号 
- BIC番号 
- BICコード 
- 銀行識別コードのための国際組織 
- Organisation internationale de normalisation 9362 
- rapide \# 
- code SWIFT 
- le numéro de swift 
- swift numéro d'acheminement 
- le numéro BIC 
- \# BIC 
- code identificateur de banque 
   
## <a name="taiwan-national-identification-number"></a>대만식 국가 식별 번호

### <a name="format"></a>형식일

1개의 문자, 9자리 숫자

### <a name="pattern"></a>패턴

1개의 문자, 9자리 숫자:
- 1개 문자(영문, 대/소문자 구분 안 함) 
- 숫자 "1" 또는 "2" 
- 8자리 숫자

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_taiwanese_national_id 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_taiwanese_national_id의 키워드가 발견되었습니다.
- 체크섬이 통과됩니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Func_taiwanese_national_id 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- 체크섬이 통과됩니다.

```xml
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
       <Pattern confidenceLevel="75">
         <IdMatch idRef="Func_taiwanese_national_id" />
       </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_taiwanese_national_id"></a>Keyword_taiwanese_national_id

- 身份證字號 
- 身份證 
- 身份證號碼 
- 身份證號 
- 身分證字號 
- 身分證 
- 身分證號碼 
- 身份證號 
- 身分證統一編號 
- 國民身分證統一編號 
- 簽名 
- 蓋章 
- 簽名或蓋章 
- 簽章   
   
## <a name="taiwan-passport-number"></a>대만 여권 번호

### <a name="format"></a>형식일

- 생체 인식 여권 번호: 9 자리 숫자
- 비-생체 인식 여권 번호: 9 자리 숫자

### <a name="pattern"></a>패턴
생체 인식 여권 번호:
- 숫자 "3"  
- 8자리 숫자

비-생체 인식 여권 번호:
- 9자리 숫자

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- 정규식 Regex_taiwan_passport 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keyword_taiwan_passport에서 키워드가 발견 되었습니다.

```xml
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_taiwan_passport"></a>Keyword_taiwan_passport

- ROC passport number 
- Passport number 
- Passport no 
- Passport Num 
- Passport # 
- 护照 
- 中華民國護照 
- Zhōnghuá Mínguó hùzhào
   
## <a name="taiwan-resident-certificate-arctarc-number"></a>대만 상주 인증서 (ARC/TARC) 번호

### <a name="format"></a>형식일

10개의 문자 및 숫자

### <a name="pattern"></a>패턴

10개의 문자 및 숫자:
- 2문자(대/소문자 구분 안 함) 
- 8자리 숫자

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- 정규식 Regex_taiwan_resident_certificate 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keyword_taiwan_resident_certificate에서 키워드가 발견 되었습니다.

```xml
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_taiwan_resident_certificate"></a>Keyword_taiwan_resident_certificate

- Resident Certificate 
- Resident Cert 
- Resident Cert. 
- Identification card 
- Alien Resident Certificate 
- ARC 
- Taiwan Area Resident Certificate 
- TARC 
- 居留證 
- 外僑居留證 
- 台灣地區居留證 

## <a name="thai-population-identification-code"></a>태국어 인구 식별 코드

### <a name="format"></a>형식일

13자리 숫자

### <a name="pattern"></a>패턴

13자리 숫자:
- 첫 번째 숫자가 0 또는 9가 아님 
- 12자리 숫자

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_Thai_Citizen_Id 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keyword_Thai_Citizen_Id에서 키워드가 발견 되었습니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Func_Thai_Citizen_Id 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.

```xml
<!-- Thai Citizen ID -->
-<Entity id="44ca9e86-ead7-4c5d-884a-e2eaa401515e" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="85">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
      <Match idRef="Keyword_Thai_Citizen_Id"/>
   </Pattern>
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_thai_citizen_id"></a>Keyword_Thai_Citizen_Id

- ID Number
- Id 번호
- บัตรประชาชน
- รหัสบัตรประชาชน
- บัตรประชาชน
- รหัสบัตรประชาชน
  
## <a name="turkish-national-identification-number"></a>터키어 국가 식별 번호

### <a name="format"></a>형식일

11자리 숫자

### <a name="pattern"></a>패턴

11자리 숫자

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_Turkish_National_Id 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keyword_Turkish_National_Id에서 키워드가 발견 되었습니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Func_Turkish_National_Id 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.

```xml
<!-- Turkish National Identity -->
-<Entity id="fb621f20-3876-4cfc-acec-8c8e73ca32c7" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="85">
      <IdMatch idRef="Func_Turkish_National_Id"/>
      <Match idRef="Keyword_Turkish_National_Id"/>
   </Pattern>
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Func_Turkish_National_Id"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_turkish_national_id"></a>Keyword_Turkish_National_Id

- TC Kimlik 아니요
- TC Kimlik numarası
- Vatandaşlık numarası
- Vatandaşlık 아니요

## <a name="uk-drivers-license-number"></a>영국 운전 면허 번호
이 중요 한 정보 유형 엔터티는 EU 드라이버의 라이선스 번호 중요 한 정보 유형에 포함 되며 독립 실행형 중요 한 정보 유형 엔터티로 사용할 수 있습니다.

### <a name="format"></a>형식일

지정된 형식의 18개 문자 및 숫자 조합

### <a name="pattern"></a>패턴

18개의 문자 및 숫자:
- 5개 문자(대/소문자 구분 안 함) 또는 문자 대신 숫자 "9" 사용 
- 1자리 숫자 
- 날짜 형식의 5 자리 숫자 MMDDY 생년월일 (드라이버가 암 인 경우 50이 고 62 51은 01부터 12까지)로 증가 합니다.
- 2개 문자(대/소문자 구분 안 함) 또는 문자 대신 숫자 "9" 사용 
- 5자리 숫자

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Func_uk_drivers_license 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_uk_drivers_license의 키워드가 발견되었습니다.
- 체크섬이 통과됩니다.

```xml
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_uk_drivers_license"></a>Keyword_uk_drivers_license

- DVLA 
- light vans 
- quadbikes 
- motor cars 
- 125cc 
- sidecar 
- tricycles 
- motorcycles 
- photocard licence 
- learner drivers 
- licence holder 
- licence holders 
- driving licences 
- driving licence 
- dual control car 
   
## <a name="uk-electoral-roll-number"></a>영국 electoral 롤 번호

### <a name="format"></a>형식일

2개의 문자, 1-4자리 숫자

### <a name="pattern"></a>패턴

2개의 문자(대/소문자 구분 안 함)와 1-4자리 숫자

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Regex_uk_electoral 정규식이 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_uk_electoral의 키워드가 발견되었습니다.

```xml
<!-- U.K. Electoral Number -->
<Entity id="a3eea206-dc0c-4f06-9e22-aa1be3059963" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_uk_electoral" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_electoral" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_uk_electoral"></a>Keyword_uk_electoral

- council nomination 
- nomination form 
- electoral register 
- electoral roll

   
## <a name="uk-national-health-service-number"></a>영국 국가 의료 서비스 번호

### <a name="format"></a>형식일

공백으로 구분된 10-17자리 숫자

### <a name="pattern"></a>패턴

10-17자리 숫자:
- 3 또는 10자리 숫자 
- 공백 
- 3자리 숫자 
- 공백 
- 4자리 숫자

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_uk_nhs_number 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- 다음 중 하나가 충족됩니다.
    - Keyword_uk_nhs_number의 키워드가 발견되었습니다.
    - Keyword_uk_nhs_number1의 키워드가 발견되었습니다.
    - Keyword_uk_nhs_number_dob의 키워드가 발견되었습니다.
- 체크섬이 통과됩니다.

```xml
<!-- U.K. NHS Number -->
<Entity id="3192014e-2a16-44e9-aa69-4b20375c9a78" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nhs_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_nhs_number" />
          <Match idRef="Keyword_uk_nhs_number1" />
          <Match idRef="Keyword_uk_nhs_number_dob" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드
   
#### <a name="keyword_uk_nhs_number"></a>Keyword_uk_nhs_number

- 국립 보건 서비스 
- nhs 
- health services authority 
- health authority

#### <a name="keyword_uk_nhs_number1"></a>Keyword_uk_nhs_number1

- patient id 
- patient identification 
- patient no 
- patient number

#### <a name="keyword_uk_nhs_number_dob"></a>Keyword_uk_nhs_number_dob

- G 
- DOB 
- D. O. B 
- Date of Birth 
- Birth Date 
   
## <a name="uk-national-insurance-number-nino"></a>영국 국가 보험 번호 (NINO)
이 중요 한 정보 유형 엔터티는 EU 국가 Identificaiton 번호 중요 한 정보 유형에 포함 되며 독립 실행형 중요 한 정보 유형 엔터티로 사용할 수 있습니다.

### <a name="format"></a>형식일

공백 또는 대시로 구분 된 7 자 또는 9 자

### <a name="pattern"></a>패턴

다음과 같은 두 가지 패턴을 사용할 수 있습니다.

- 두 문자 (유효한 NINOs이 접두사의 특정 문자만 사용 하며이 패턴의 유효성 검사는 대/소문자를 구분 하지 않음)
- 6자리 숫자
- ' A ', ' B ', ' C ' 또는 ' d ' (접두사와 마찬가지로 접미사에서는 특정 문자만 허용 되며 대/소문자 구분 안 함)

또는

- 2 개 문자
- 공백 또는 대시
- 2자리 숫자
- 공백 또는 대시
- 2자리 숫자
- 공백 또는 대시
- 2자리 숫자
- 공백 또는 대시
- ' A ', ' B ', ' C ' 또는 ' d ' 중 하나

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_uk_nino 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_uk_nino의 키워드가 발견되었습니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Func_uk_nino 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_uk_nino의 키워드가 발견되지 않았습니다.

```xml
<!-- U.K. NINO -->
<Entity id="16c07343-c26f-49d2-a987-3daf717e94cc" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nino" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_nino" />
        </Any>
    </Pattern>    
     <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_nino" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_uk_nino" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_uk_nino"></a>Keyword_uk_nino

- national insurance number

- national insurance contributions

- protection act
- 소유권
- social security number

- insurance application

- medical application

- social insurance

- medical attention

- 소셜 보안
- great britain
- 소유권
    
## <a name="uk-tax-identification-number"></a>영국 세금 식별 번호
이 중요 한 정보 유형 엔터티는 EU 세금 식별 번호로 중요 한 정보 유형 으로만 사용할 수 있습니다.


### <a name="format"></a>형식일

UTR (Unique Taxpayer Reference): 공백 및 구분 기호가 없는 10 자리 숫자
 
  
### <a name="pattern"></a>패턴

UTR (Unique Taxpayer Reference): 10 자리 숫자

  
### <a name="checksum"></a>제외

예
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
  
- 이 함수는 해당  `Func_uk_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
- From 키워드를  `Keywords_uk_eu_tax_file_number` 찾았습니다. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_uk_eu_tax_file_number"></a>Keywords_uk_eu_tax_file_number

- 세금 번호
- 세금 파일
- tax id

- 세금 식별 아니요
- 세금 식별 번호
- 세금 없음 #
- 세금 없음
- 세금 등록 번호
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- 언급 id
- 언급 아니요
- 언급 #

## <a name="us-bank-account-number"></a>미국 은행 계좌 번호

### <a name="format"></a>형식일

8-17자리 숫자

### <a name="pattern"></a>패턴

8-17자리 연속 숫자

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Regex_usa_bank_account_number 정규식이 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_usa_Bank_Account의 키워드가 발견되었습니다.

```xml
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_usa_bank_account"></a>Keyword_usa_Bank_Account

- Checking Account Number 
- Checking Account 
- Checking Account # 
- Checking Acct Number 
- Checking Acct # 
- Checking Acct No. 
- Checking Account No. 
- Bank Account Number 
- Bank Account # 
- Bank Acct Number 
- Bank Acct # 
- Bank Acct No. 
- Bank Account No. 
- Savings Account Number 
- Savings Account. 
- Savings Account # 
- Savings Acct Number 
- Savings Acct # 
- Savings Acct No. 
- Savings Account No. 
- Debit Account Number 
- Debit Account 
- Debit Account # 
- Debit Acct Number 
- Debit Acct # 
- Debit Acct No. 
- Debit Account No. 

## <a name="us-drivers-license-number"></a>미국 운전 면허 번호

### <a name="format"></a>형식일

주마다 다릅니다.

### <a name="pattern"></a>패턴

주마다 다릅니다(예: 뉴욕).
- Ddd ddd ddd와 같이 9 자리 숫자는 일치 합니다.
- Ddddddddd와 같은 9 자리 숫자가 일치 하지 않습니다.

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Func_new_york_drivers_license_number 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_[state_name]_drivers_license_name의 키워드가 발견되었습니다.
- Keyword_us_drivers_license에서 키워드가 발견 되었습니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 65% 신뢰합니다.
- Func_new_york_drivers_license_number 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_[state_name]_drivers_license_name의 키워드가 발견되었습니다.
- Keyword_us_drivers_license_abbreviations의 키워드가 발견되었습니다.
- Keyword_us_drivers_license의 키워드가 발견되지 않았습니다.

```xml
<Entity id="dfeb356f-61cd-459e-bf0f-7c6d28b458c6 patternsProximity="300">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license" />
    </Pattern>
    <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license_abbreviations" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_us_drivers_license" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_us_drivers_license_abbreviations"></a>Keyword_us_drivers_license_abbreviations

- DL 
- 된다 
- CDL 
- CDLS 
- ID 
- 번호가 
- DL # 
- 된다 # 
- CDL # 
- CDLS # 
- I #
- 번호가 # 
- ID number 
- ID numbers 
- LIC 
- LIC # 

#### <a name="keyword_us_drivers_license"></a>Keyword_us_drivers_license

- DriverLic 
- DriverLics 
- DriverLicense 
- DriverLicenses 
- Driver Lic 
- Driver Lics 
- Driver License 
- Driver Licenses 
- DriversLic 
- DriversLics 
- 드라이버 라이선스 
- 드라이버 라이선스 
- Drivers Lic 
- Drivers Lics 
- Drivers License 
- Drivers Licenses 
- Driver' Lic 
- Driver'Lics 
- Driver' 라이선스 
- Driver'Licenses 
- Driver' Lic 
- Driver' Lics 
- Driver' License 
- Driver' Licenses
- Driver'sLic 
- Drivers (Slics) 
- Driver'sLicense 
- Driver'sLicenses 
- Driver's Lic 
- Driver's Lics 
- Driver's License 
- Driver's Licenses 
- identification number 
- identification numbers 
- identification # 
- id card 
- id cards 
- identification card 
- identification cards 
- DriverLic # 
- DriverLics # 
- DriverLicense # 
- DriverLicenses # 
- Driver Lic# 
- Driver Lics# 
- Driver License# 
- Driver Licenses# 
- DriversLic # 
- DriversLics # 
- 드라이버 라이선스 # 
- 드라이버 라이선스 # 
- Drivers Lic# 
- Drivers Lics# 
- Drivers License# 
- Drivers Licenses# 
- Driver' Lic # 
- Driver'Lics # 
- Driver' 라이선스 # 
- Driver'Licenses # 
- Driver' Lic# 
- Driver' Lics# 
- Driver' License# 
- Driver' Licenses# 
- Driver'sLic # 
- Drivers (Slics) # 
- Driver'sLicense # 
- Driver'sLicenses # 
- Driver's Lic# 
- Driver's Lics# 
- Driver's License# 
- Driver's Licenses# 
- id card# 
- id cards# 
- identification card# 
- identification cards# 


#### <a name="keyword_state_name_drivers_license_name"></a>Keyword_ [state_name] _drivers_license_name

- 주 약어(예: "NY") 
- 주 이름(예: "New York")

## <a name="us-individual-taxpayer-identification-number-itin"></a>미국 ITIN (개별 taxpayer 식별 번호)

### <a name="format"></a>형식일

"9"로 시작되고, "7" 또는 "8"을 4번째 숫자로 포함하고, 경우에 따라 공백이나 대시로 서식이 지정된 9자리 숫자

### <a name="pattern"></a>패턴

서식이
- "9"자리 숫자 
- 2자리 숫자 
- 공백 또는 대시 
- "7" 또는 "8" 
- 1자리 숫자 
- 공백 또는 대시 
- 4자리 숫자

서식
- "9"자리 숫자 
- 2자리 숫자 
- "7" 또는 "8" 
- 5자리 숫자

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_formatted_itin 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- 다음 중 하나 이상이 충족됩니다.
    - Keyword_itin의 키워드가 발견되었습니다.
    - Func_us_address 함수가 올바른 날짜 형식의 주소를 찾습니다.
    - Func_us_date 함수가 올바른 날짜 형식의 날짜를 찾습니다.
    - Keyword_itin_collaborative의 키워드가 발견되었습니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Func_unformatted_itin 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- 다음 중 하나 이상이 충족됩니다.
    - Keyword_itin_collaborative의 키워드가 발견되었습니다.
    - Func_us_address 함수가 올바른 날짜 형식의 주소를 찾습니다.
    - Func_us_date 함수가 올바른 날짜 형식의 날짜를 찾습니다.

```xml
<!-- U.S. Individual Taxpayer Identification Number (ITIN) -->
<Entity id="e55e2a32-f92d-4985-a35d-a0b269eb687b" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_formatted_itin" />
        <Any minMatches="1">
          <Match idRef="Keyword_itin" />
          <Match idRef="Func_us_address" />
          <Match idRef="Func_us_date" />
          <Match idRef="Keyword_itin_collaborative" />
        </Any>
    </Pattern>
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_itin" />
        <Match idRef="Keyword_itin" />
        <Any minMatches="1">
          <Match idRef="Keyword_itin_collaborative" />
          <Match idRef="Func_us_address" />
          <Match idRef="Func_us_date" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_itin"></a>Keyword_itin

- taxpayer 
- tax id 
- tax identification 
- itin 
- ssn 
- 언급 
- social security 
- tax payer 
- itins 
- taxid 
- individual taxpayer 

#### <a name="keyword_itin_collaborative"></a>Keyword_itin_collaborative

- License 
- DL 
- DOB 
- 생년월일 
- 생일 
- Date of Birth 

## <a name="us-social-security-number-ssn"></a>미국 SSN (사회 보장 번호)

### <a name="format"></a>형식일

서식 있는 패턴 또는 서식 없는 패턴으로 표시될 수 있는 9자리 숫자

> [!NOTE]
> Mid가 2011 이전에 실행 된 경우 SSN은 특정 범위 내에서 번호의 특정 부분이 유효한 지 확인 하는 강력한 서식을 사용 해야 하지만 검사 값은 없습니다.

### <a name="pattern"></a>패턴

다음의 네 가지 패턴에서 SSNs를 검색 하는 함수는 다음과 같습니다.
- Func_ssn는 대시 또는 공백으로 서식이 지정 된 2011 이전 수준의 서식으로 SSNs를 찾습니다 (ddd-dd-dddd 또는 ddd dd dddd).
- Func_unformatted_ssn는 형식이 지정 되지 않은 2011 이전 형식으로 서식이 지정 된 SSNs를 찾고 (ddddddddd)
- Func_randomized_formatted_ssn는 대시 또는 공백으로 서식이 지정 된 post-2011 SSNs를 찾습니다 (ddd-dd-dddd 또는 ddd dd dddd).
- Func_randomized_unformatted_ssn는 형식 없는 2011 SSNs를 찾습니다 (ddddddddd).

### <a name="checksum"></a>제외

아니요


### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_ssn 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_ssn의 키워드가 발견되었습니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Func_unformatted_ssn 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keyword_ssn의 키워드가 발견되었습니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 65% 신뢰합니다.
- Func_randomized_formatted_ssn 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_ssn의 키워드가 발견되었습니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 55% 신뢰합니다.
- Func_randomized_unformatted_ssn 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_ssn의 키워드가 발견되었습니다.


```xml
<!-- U.S. Social Security Number (SSN) -->
  <Entity id="a44669fe-0d48-453d-a9b1-2cc83f2cba77" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_randomized_formatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="55">
        <IdMatch idRef="Func_randomized_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
  </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_ssn"></a>Keyword_ssn

- Social Security 
- Social Security# 
- Soc Sec 
- SSN 
- 있는 SSN 
- SSN # 
- 대비 # 
- 생길 
   
## <a name="us--uk-passport-number"></a>미국/영국 passport number
영국 passport 번호 중요 한 정보 유형 엔터티는 EU 여권 번호 중요 한 정보 유형으로 제공 되며 독립 실행형 중요 한 정보 유형 엔터티로 사용할 수 있습니다.

### <a name="format"></a>형식일

9자리 숫자

### <a name="pattern"></a>패턴

9자리 연속 숫자

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Func_usa_uk_passport 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_passport의 키워드가 발견되었습니다.

```xml
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_passport"></a>Keyword_passport

- Passport Number 
- Passport No 
- Passport # 
- 여권 # 
- PassportID 
- Passportno 
- passportnumber 
- パスポート 
- パスポート番号 
- パスポートのNum 
- パスポート＃ 
- Numéro de passeport 
- Passeport n ° 
- Passeport Non 
- Passeport # 
- 포트 # 
- 지/포트 아님 
- Passeportn ° 
