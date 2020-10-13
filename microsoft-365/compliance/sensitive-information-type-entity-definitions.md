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
ms.openlocfilehash: adc1006628b8b4f13d30f2001fee0871b51b18ca
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430435"
---
# <a name="sensitive-information-type-entity-definitions"></a>중요한 정보 유형 엔터티 정의

준수 센터의 DLP (데이터 손실 방지)에는 DLP 정책에서 사용할 수 있는 중요 한 정보 유형이 많이 포함 되어 있습니다. 이 항목에서는 이러한 모든 중요한 정보 유형의 목록과 DLP 정책이 이러한 각 유형을 검색할 때 찾는 내용을 보여 줍니다. 중요한 정보 유형은 정규식이나 함수로 식별될 수 있는 패턴으로 정의됩니다. 또한 키워드 및 체크섬과 같은 확증적인 증거를 사용하여 중요한 정보 유형을 식별할 수 있습니다. 이러한 평가 프로세스에서 신뢰 수준 및 근접성도 사용됩니다.

중요 한 정보 유형에는 다음 구독 중 하나가 필요 합니다.
- Microsoft 365 E3
- Microsoft 365 E5

## <a name="aba-routing-number"></a>ABA 라우팅 번호

### <a name="format"></a>형식일

서식이 지정 되거나 서식 없는 패턴으로 표시 될 수 있는 9 자리 숫자

### <a name="pattern"></a>패턴

서식이
- 0, 1, 2, 3, 6, 7 또는 8로 시작 하는 4 자리 숫자
- 하이픈
- 4 자리 숫자
- 하이픈
- 숫자

서식 없음: 0, 1, 2, 3, 6, 7 또는 8로 시작 하는 연속 9 자리 숫자 

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

#### <a name="keyword_aba_routing"></a>Keyword_aba_routing

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
- 2 자리 숫자
- 마침표
- 3 자리 숫자
- 마침표
- 3 자리 숫자

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

뱅크 상태 번호를 포함 하거나 제외 하 고 6 ~ 10 자리 숫자

### <a name="pattern"></a>패턴

계정 번호는 6 ~ 10 자리 숫자입니다.

호주 은행 지점 번호:
- 3 자리 숫자 
- 하이픈 
- 3 자리 숫자

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

## <a name="australia-business-number"></a>오스트레일리아 근무처 번호
이 중요 한 정보 유형은 다음 에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거 버 넌 스
- 레코드 관리
- Microsoft cloud app security


### <a name="format"></a>형식일

선택적 구분 기호가 있는 11 자리 숫자

### <a name="pattern"></a>패턴

선택적 구분 기호가 있는 11 자리 숫자:

- 2 자리 숫자
- 선택적 하이픈 또는 공백
- 3 자리 숫자
- 선택적 하이픈 또는 공백
- 3 자리 숫자
- 선택적 하이픈 또는 공백
- 3 자리 숫자

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_australian_business_number 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keywords_australian_business_number에서 키워드가 발견 되었습니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Func_australian_business_number 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.

```xml
      <!-- Australia Business Number -->
      <Entity id="76e83b3b-01ee-4530-aced-e667a6609f49" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_australian_business_number" />
          <Match idRef="Keywords_australian_business_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_australian_business_number" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>키워드

#### <a name="keyword_australia_business_number"></a>Keyword_australia_business_number

- 오스트레일리아 business 아니요
- 근무처 번호
- abn #
- businessid #
- 비즈니스 id
- abn
- businessno #

## <a name="australia-company-number"></a>오스트레일리아 회사 번호
이 중요 한 정보 유형은 다음 에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거 버 넌 스
- 레코드 관리
- Microsoft cloud app security

### <a name="format"></a>형식일

구분 기호가 있는 9 자리 숫자

### <a name="pattern"></a>패턴

구분 기호가 있는 9 자리 숫자:

- 3 자리 숫자
- 공백
- 3 자리 숫자
- 공백
- 3 자리 숫자


### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_Australian_Company_Number 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keyword_Australian_Company_Number에서 키워드가 발견 되었습니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 65% 신뢰합니다.
- Func_Australian_Company_Number 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.

```xml
      <!-- Australia Company Number -->
      <Entity id="b1fba4f7-7b3e-4bb9-8f9a-9366df604dbb" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_Australian_Company_Number" />
          <Match idRef="Keyword_Australian_Company_Number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_Australian_Company_Number" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>키워드

#### <a name="keyword_australia_company_number"></a>Keyword_australia_company_number

- 될
- 오스트레일리아 회사 번호
- 오스트레일리아 회사 번호 #
- 오스트레일리아 회사 번호
- 오스트레일리아 company 아니요
- 오스트레일리아 company 아니요 #
- 오스트레일리아 회사 번호

## <a name="australia-drivers-license-number"></a>오스트레일리아 운전 면허 번호

### <a name="format"></a>형식일

9 개의 문자 및 숫자

### <a name="pattern"></a>패턴

9 개의 문자 및 숫자: 

- 2 자리 숫자 또는 문자 (대/소문자 구분 안 함) 
- 2 자리 숫자 
- 5 자리 숫자 또는 문자 (대/소문자 구분 안 함)

또는

- 1 ~ 2 개의 선택적 문자 (대/소문자 구분 안 함) 
- 4 ~ 9 자리 숫자

또는

- 9 자리 숫자 또는 문자 (대/소문자 구분 안 함)

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
- 9 번째 숫자는 검사 숫자입니다.
- 10 번째 숫자는 문제 숫자입니다.
- 11 번째 숫자 (선택 사항)는 개별 숫자입니다.

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

8 ~ 9 자리 숫자

### <a name="pattern"></a>패턴

일반적으로 다음과 같이 공백을 사용 하 여 표시 되는 8 자리 숫자입니다.
- 3 자리 숫자 
- 선택적 공백 
- 3 자리 숫자 
- 선택적 공백 
- 마지막 숫자가 검사 숫자인 2 ~ 3 자리 숫자

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
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_australia_tax_file_number"></a>Keyword_australia_tax_file_number

- australian business number
- marginal tax rate
- medicare levy
- portfolio number
- service veterans
- withholding tax
- individual tax return
- tax file number
- tfn

## <a name="austria-drivers-license-number"></a>오스트리아 드라이버의 라이선스 번호
이 중요 한 정보 유형 엔터티는 EU 드라이버의 라이선스 번호 중요 정보 유형 에서만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백과 구분 기호가 없는 8 자리 숫자
  
### <a name="pattern"></a>패턴

8 자리 숫자
  
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

#### <a name="keywords_austria_eu_drivers_license_number"></a>Keywords_austria_eu_driver ' s_license_number

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

## <a name="austria-identity-card"></a>오스트리아 id 카드
이 중요 한 정보 유형은 다음 에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거 버 넌 스
- 레코드 관리
- Microsoft cloud app security

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
      <!-- Austria Identity Card -->
      <Entity id="5ec06c3b-007e-4820-8343-7ff73b889735" patternsProximity="300" recommendedConfidence="75">
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
  
- 1 개 문자 (대/소문자 구분 안 함)
- 1 개의 공백 (선택 사항)
- 7 자리 숫자
    
### <a name="checksum"></a>제외

해당 없음
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- 정규식이 해당  `Regex_austria_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_austria_eu_passport_number` 찾았습니다. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_austria_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- 여권 #
- 여권 #
- passportid
- passports
- passportno
- passport 아니요
- passportnumber
- 여권 번호
- passportnumbers
- 여권 번호

#### <a name="keywords_austria_eu_passport_number"></a>Keywords_austria_eu_passport_number

- reisepassnummer
- reisepasse
- No-Reisepass 
- Nr-Reisepass
- Reisepass-Nr
- Passnummer
- reisepässe

## <a name="austria-social-security-number-or-equivalent-identification"></a>오스트리아 주민 등록 번호 또는 동등한 식별
이 중요 한 정보 유형 엔터티는 EU 주민 등록 번호 또는 해당 ID 중요 정보 유형에 서만 사용할 수 있습니다.

### <a name="format"></a>형식일

지정 된 형식의 10 자리 숫자
  
### <a name="pattern"></a>패턴

10자리 숫자:
  
- 일련 번호에 해당 하는 3 자리 숫자 
- 검사 숫자 1 개
- 생년월일에 해당 하는 6 자리 숫자 (DDMMYY)
    
### <a name="checksum"></a>제외

예
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- 함수 ' Func_austria_eu_
- _or_equivalent '는 해당 패턴과 일치 하는 콘텐츠를 찾습니다. 
- from 키워드를  `Keywords_austria_eu_ssn_or_equivalent` 찾았습니다. 
    
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

### <a name="format"></a>형식일

하이픈 및 슬래시가 있는 9 자리 숫자
  
### <a name="pattern"></a>패턴

하이픈 및 슬래시가 있는 9 자리 숫자:
  
- 2 자리 숫자
- 하이픈 (선택 사항)
- 3 자리 숫자
- 슬래시 (선택 사항)
- 4 자리 숫자
    
### <a name="checksum"></a>제외

예
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- 이 함수는 해당  `Func_austria_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_austria_eu_tax_file_number` 찾았습니다. 
    
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 65% 신뢰합니다.
- 이 함수는 해당  `Func_austria_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
```xml
      <!-- Austria Tax Identification Number -->
      <Entity id="4fd58d22-af28-4451-b18a-6f722430a56d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
          <Match idRef="Keywords_austria_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
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
 
## <a name="austria-value-added-tax"></a>오스트리아 값 추가 된 세금
이 중요 한 정보 유형은 다음 에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거 버 넌 스
- 레코드 관리
- Microsoft cloud app security

### <a name="format"></a>형식일

11 자리 영숫자 패턴

### <a name="pattern"></a>패턴

11 자리 영숫자 패턴:

- A 또는 a
- T 또는 t
- 선택적 공간
- U 또는 u
- 선택적 공간
- 2 ~ 3 자리 숫자
- 선택적 공간
- 4 자리 숫자
- 선택적 공간
- 1 ~ 2 자리 숫자

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_Austria_Value_Added_Tax 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keyword_Austria_Value_Added_Tax에서 키워드가 발견 되었습니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Func_Austria_Value_Added_Tax 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.

```xml
      <!-- Austria Value Added Tax -->
      <Entity id="b6a3eda2-c56c-4b69-a5f7-dca34db00f48" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_Austria_Value_Added_Tax" />
          <Match idRef="Keyword_Austria_Value_Added_Tax" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_Austria_Value_Added_Tax" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>키워드

#### <a name="keyword_austria_value_added_tax"></a>Keyword_austria_value_added_tax

- vat 번호
- vat #
- 오스트리아 vat 번호
- vat 번호
- vatno #
- 값이 추가 된 세금 번호
- 오스트리아-vat
- mwst
- umsatzsteuernummer
- mwstnummer
- ust.-identifikationsnummer
- umsatzsteuer-identifikationsnummer
- vat 식별 번호
- atu 번호
- uid 번호


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
- 0 ~ 2 개의 공백 문자
- 등호 (=)
- 0 ~ 2 개의 공백 문자
- 1-200에서 대/소문자, 숫자, 기호, 특수 문자 또는 공백 사이의 조합
- 문자열 "cloudapp.<!--no-hyperlink-->com "," cloudapp.<!--no-hyperlink-->net "또는" database.<!--no-hyperlink-->투자
- 1-300에서 대/소문자, 숫자, 기호, 특수 문자 또는 공백 사이의 조합
- 문자열 "Password", "password" 또는 "pwd"
- 0 ~ 2 개의 공백 문자
- 등호 (=)
- 0 ~ 2 개의 공백 문자
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

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

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
- 0 ~ 2 개의 공백 문자
- 등호 (=)
- 0 ~ 2 개의 공백 문자
- 1-200에서 대/소문자, 숫자, 기호, 특수 문자 또는 공백 사이의 조합
- 문자열 "azure-장치<!--no-hyperlink-->투자
- 1-200에서 대/소문자, 숫자, 기호, 특수 문자 또는 공백 사이의 조합
- "SharedAccessKey" 문자열
- 0 ~ 2 개의 공백 문자
- 등호 (=)
- 0 ~ 2 개의 공백 문자
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

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

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

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

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
- 0 ~ 2 개의 공백 문자
- 등호 (=)
- 0 ~ 2 개의 공백 문자
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

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

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
- 0 ~ 2 개의 공백 문자
- 등호 (=)
- 0 ~ 2 개의 공백 문자
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

## <a name="azure-service-bus-connection-string"></a>Azure service bus 연결 문자열

### <a name="format"></a>형식일

문자열 "끝점" 뒤에 "servicebus" 라는 문자열을 포함 하 여 아래 패턴에 나와 있는 문자 및 문자열이 표시 됩니다.<!--no-hyperlink-->net "및" SharedAccesKey "을 차례로 누릅니다.

### <a name="pattern"></a>패턴

- 문자열 "끝점"
- 0 ~ 2 개의 공백 문자
- 등호 (=)
- 0 ~ 2 개의 공백 문자
- 1-200에서 대/소문자, 숫자, 기호, 특수 문자 또는 공백 사이의 조합
- 문자열 "servicebus.<!--no-hyperlink-->투자
- 1-200에서 대/소문자, 숫자, 기호, 특수 문자 또는 공백 사이의 조합
- "SharedAccessKey" 문자열
- 0 ~ 2 개의 공백 문자
- 등호 (=)
- 0 ~ 2 개의 공백 문자
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

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

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
- 0 ~ 2 개의 공백 문자
- 등호 (=)
- 0 ~ 2 개의 공백 문자
- 1-200에서 대/소문자, 숫자, 기호, 특수 문자 또는 공백 사이의 조합
- 문자열 "AccountKey"
- 0 ~ 2 개의 공백 문자
- 등호 (=)
- 0 ~ 2 개의 공백 문자
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

#### <a name="cep_azure_emulator_storage_account_filter"></a>CEP_azure_emulator_storage_account_filter

기술적으로이 중요 한 정보 유형은 키워드 목록이 아니라 정규식을 사용 하 여 이러한 키워드를 식별 합니다.

- Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw = =

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

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

- 0은 보다 큼 기호 (>), 아포스트로피 ('), 등호 (=), 따옴표 (") 또는 숫자 기호 (#) 중 하나입니다.
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

10 자리 숫자
  
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

### <a name="format"></a>형식일

11 자리 숫자와 선택적 구분 기호

### <a name="pattern"></a>패턴

11자리 숫자와 구분 기호:
- 6 자리 숫자와 2 개의 선택적 마침표 (YY) 19. DD for 생년월일 
- 점, 대시, 공백 등의 선택적 구분 기호 
- 3 개의 순차 숫자 (남성의의 경우 홀수, 여성의 경우 짝수의 경우에도) 
- 점, 대시, 공백 등의 선택적 구분 기호 
- 두 개의 검사 숫자

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Func_belgium_national_number 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keyword_belgium_national_number에서 키워드가 발견 되었습니다.
- 체크섬이 통과됩니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 65% 신뢰합니다.
- Func_belgium_national_number 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- 체크섬이 통과됩니다.

```xml
<!-- Belgium National Number -->
       <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_national_number" />
          <Match idRef="Keyword_belgium_national_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_belgium_national_number" />
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
- 주민 등록 번호
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

해당 없음
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- 정규식이 해당  `Regex_belgium_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_belgium_eu_passport_number` 찾았습니다.

```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_belgium_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- 여권 #
- 여권 #
- passportid
- passports
- passportno
- passport 아니요
- passportnumber
- 여권 번호
- passportnumbers
- 여권 번호

#### <a name="keywords_belgium_eu_passport_number"></a>Keywords_belgium_eu_passport_number

- numéro (고) 포트
- 고 대 veiligheid
- veiligheid
- paspoortnummer
- paspoortnummers
- 포트 carte
- 포트 livre
- Pass-Nr
- Passnummer
- reisepass kein

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


## <a name="belgium-value-added-tax-number"></a>벨기에 값 세금 번호 추가 됨
이 중요 한 정보 유형은 다음 에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거 버 넌 스
- 레코드 관리
- Microsoft cloud app security

### <a name="format"></a>형식일

12 자리 영숫자 패턴

### <a name="pattern"></a>패턴

12 자리 영숫자 패턴:

- a 문자 B 또는 b
- 문자 E 또는 e
- 숫자 0
- 1부터 9 까지의 숫자입니다.
- 선택적 점 또는 하이픈 또는 공백
- 4 자리 숫자
- 선택적 점 또는 하이픈 또는 공백
- 4 자리 숫자


### <a name="checksum"></a>제외

예


### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_belgium_value_added_tax_number 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keywords_belgium_value_added_tax_number에서 키워드가 발견 되었습니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Func_belgium_value_added_tax_number 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.

```xml
      <!-- Belgium Value Added Tax Number -->
      <Entity id="85b5b3c3-f2de-4ae8-ac46-fd3cb38bf9ed" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_belgium_value_added_tax_number" />
          <Match idRef="Keywords_belgium_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_value_added_tax_number" />
        </Pattern>
      </Entity>
    </Version>
```
### <a name="keywords"></a>키워드

#### <a name="keyword_belgium_value_added_tax_number"></a>Keyword_belgium_value_added_tax_number

- n º va
- vat 번호
- vat 아니요
- numéro
- umsatzsteuer-identifikationsnummer
- umsatzsteuernummer
- btw
- btw #
- vat #


## <a name="brazil-cpf-number"></a>브라질 CPF 번호

### <a name="format"></a>형식일

서식이 있거나 서식이 없을 수 있는 검사 숫자를 포함하는 11자리 숫자

### <a name="pattern"></a>패턴

서식이
- 3 자리 숫자
- 마침표
- 3 자리 숫자
- 마침표
- 3 자리 숫자
- 하이픈
- 검사 숫자에 해당 하는 2 자리 숫자

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

- 2 자리 숫자 
- 마침표 
- 3 자리 숫자 
- 마침표 
- 3 자리 숫자 (처음 8 자리 숫자는 등록 번호) 
- 슬래시 
- 4 자리 지점 번호 
- 하이픈 
- 검사 숫자에 해당 하는 2 자리 숫자

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
- Business 
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
- 2 자리 숫자 
- 마침표 
- 3 자리 숫자 
- 마침표 
- 3 자리 숫자 
- 하이픈 
- 검사 숫자에 해당 하는 1 자리 숫자

Registro de Identidade (RIC) (새 형식):
- 10 자리 숫자 
- 하이픈 
- 검사 숫자에 해당 하는 1 자리 숫자

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

9 자리 숫자
  
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

#### <a name="keywords_bulgaria_eu_drivers_license_number"></a>Keywords_bulgaria_eu_driver ' s_license_number
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


## <a name="bulgaria-uniform-civil-number"></a>불가리아 uniform 민사 번호
이 중요 한 정보 유형은 다음 에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거 버 넌 스
- 레코드 관리
- Microsoft cloud app security

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
- From 키워드를  `Keywords_bulgaria_eu_national_id_card` 찾았습니다. 

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- 이 함수는 해당  `Func_bulgaria_eu_national_id_card` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
```xml
      <!-- Bulgaria Uniform Civil Number -->
      <Entity id="100d58b1-0a35-4fb1-aa89-e4a86fb53fcc" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
          <Match idRef="Keywords_bulgaria_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_bulgaria_eu_telephone_number" />
            <Match idRef="Keywords_bulgaria_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_bulgaria_eu_national_id_card"></a>Keywords_bulgaria_eu_national_id_card

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
- 주민 등록 번호
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

9 자리 숫자 
  
### <a name="checksum"></a>제외

아니요
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- 정규식이 해당  `Regex_bulgaria_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From  `Keywords_bulgaria_eu_passport_number` 또는 found의 키워드 `Keywords_eu_passport_number_common` 입니다. 

```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_bulgaria_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```
### <a name="keywords"></a>키워드

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- 여권 #
- 여권 #
- passportid
- passports
- passportno
- passport 아니요
- passportnumber
- 여권 번호
- passportnumbers
- 여권 번호

#### <a name="keywords_bulgaria_eu_passport_number"></a>Keywords_bulgaria_eu_passport_number

- номер на паспорта
- номер на паспорт
- паспорт 아니요

## <a name="canada-bank-account-number"></a>캐나다 은행 계좌 번호

### <a name="format"></a>형식일

7 또는 12 자리 숫자

### <a name="pattern"></a>패턴

캐나다 은행 계좌 번호는 7 또는 12자리 숫자입니다.

캐나다 은행 계좌 송금 번호:
- 5 자리 숫자 
- 하이픈 
- 3 자리 숫자 또는
- 제로 "0" 
- 8 자리 숫자

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

10 자리 숫자

### <a name="pattern"></a>패턴

10 자리 숫자

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

두 개의 대문자와 6 자리 숫자

### <a name="pattern"></a>패턴

두 개의 대문자와 6 자리 숫자

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

9 자리 숫자

### <a name="pattern"></a>패턴

9 자리 숫자

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Regex_canada_phin 정규식이 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_canada_phin 또는 Keyword_canada_provinces에서 키워드가 두 개 이상 있습니다.

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

선택적 하이픈 또는 공백이 있는 9 자리 숫자

### <a name="pattern"></a>패턴

서식이
- 3 자리 숫자 
- 하이픈 또는 공백 
- 3 자리 숫자 
- 하이픈 또는 공백 
- 3 자리 숫자

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

7 ~ 8 자리 숫자와 구분 기호, 검사 숫자 또는 문자

### <a name="pattern"></a>패턴

7 ~ 8 자리와 구분 기호:
- 1 ~ 2 자리 숫자 
- 마침표 
- 3 자리 숫자 
- 마침표 
- 3 자리 숫자 
- 대시 
- 검사 숫자에 해당 하는 1 자리 숫자 또는 문자 (대/소문자 구분 안 함)

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
- 주소 코드에 해당 하는 6 자리 숫자 
- 생년월일에 해당 하는 YYYYMMDD 형식의 8 자리 숫자 
- 주문 코드에 해당 하는 3 자리 숫자 
- 검사 숫자에 해당 하는 1 자리 숫자

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

- 
card verification

- card identification number
- cvn
- cid
- cvc2
- cvv2
- 
pin block
- security code

- security number

- security no

- issue number

- issue no
- cryptogramme
- 
numéro de sécurité
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
- cod.sicurezza
- 
cod sicurezza
- n autorizzazione
- código
- codigo
- cod.seg
- 
cod seg
- código de segurança

- codigo de seguranca

- codigo de segurança

- código de seguranca
- cód.segurança
- cod.seguranca
- cod.segurança
- cód.seguranca
- cód segurança
- cod seguranca
- cod segurança
- cód seguranca
- número de verificação

- numero de verificacao
- ablauf
- gültig bis
- gültigkeitsdatum
- gultig bis
- gultigkeitsdatum
- scadenza
- 
data scad
- fecha de expiracion

- fecha de venc
- vencimiento
- 
válido hasta
- valido hasta
- vto
- 
data de expiração
- data de expiracao

- data em que expira
- 유효한 ade
- valor
- vencimento
- transaction
- 거래 번호
- 참조 번호
- セキュリティコード
- セキュリティ コード
- セキュリティナンバー
- セキュリティ ナンバー
- セキュリティ番号

#### <a name="keyword_cc_name"></a>Keyword_cc_name

- amex
- american express
- americanexpress
- americano espresso

- Visa
- mastercard
- master card
- mc
- mastercards
- 
master cards
- 식사 권을의 방망이
- diners club
- dinersclub
- 찾아보십시오
- discover card
- discovercard
- discover cards
- JCB
- BrandSmart
- japanese card bureau

- carte blanche
- carteblanche
- 신용 카드
- 참조란 #
- 참조 #:
- 
expiration date
- exp date

- 
expiry date
- 
date d’expiration
- 
date d'exp
- 
date expiration
- bank card
- bankcard
- 
card number
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
- 
en route
- card type

- 회원 계정
- 회원 계정
- Card no
- 회사 카드
- 회사 카드
- 카드 유형
- 카드 계정 번호
- 카드 구성원 계정
- 구성원 계정입니다.
- card no.

- 카드 번호
- card number

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
- 
carta di credito
- carta credito
- kn.카 ta
- n carta
- veiligheid.카 ta
- 
nr carta
- numero carta

- numero della carta

- numero di carta

- tarjeta credito

- tarjeta de credito

- 
tarjeta crédito
- 
tarjeta de crédito
- tarjeta de atm

- tarjeta atm

- tarjeta debito

- tarjeta de debito

- 
tarjeta débito
- 
tarjeta de débito
- nº de tarjeta
- 아니요.de tarjeta
- de tarjeta
- numero de tarjeta

- número de tarjeta

- tarjeta no
- tarjetahabiente
- 
cartão de crédito
- cartão de credito

- cartao de crédito

- cartao de credito

- cartão de débito

- cartao de débito

- cartão de debito

- cartao de debito

- débito automático
- debito automatico

- 
número do cartão
- numero do cartão

- número do cartao

- numero do cartao

- número de cartão

- numero de cartão

- número de cartao

- numero de cartao

- n º cartão
- nº do cartao
- n ºdo cartão
- do no cartão
- 작업 없음
- 아니요.do cartão
- 아니요.do cartao
- クレジットカード番号
- クレジットカードナンバー
- クレジットカード＃
- クレジットカード
- クレジット
- クレカ
- カード番号
- カードナンバー
- カード＃
- アメックス
- アメリカンエクスプレス
- アメリカン エクスプレス
- Visaカード
- カード
- マスターカード
- マスター カード
- マスター
- ダイナースクラブ
- ダイナース クラブ
- ダイナース
- 有効期限
- 期限
- キャッシュカード
- キャッシュ カード
- カード名義人
- カードの名義人
- カードの名義
- デビット カード
- デビットカード


## <a name="croatia-drivers-license-number"></a>크로아티아 운전 면허 번호
이 중요 한 정보 유형 엔터티는 EU 드라이버의 라이선스 번호 중요 정보 유형 에서만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백과 구분 기호가 없는 8 자리 숫자
  
### <a name="pattern"></a>패턴

8 자리 숫자
  
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

#### <a name="keywords_croatia_eu_drivers_license_number"></a>Keywords_croatia_eu_driver ' s_license_number

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

9 자리 숫자

### <a name="pattern"></a>패턴

9 자리 연속 숫자

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

9 자리 숫자 
  
### <a name="checksum"></a>제외

아니요
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- 정규식이 해당  `Regex_croatia_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From  `Keywords_eu_passport_number_common` 또는 found의 키워드 `Keywords_croatia_eu_passport_number` 입니다. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_croatia_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```
### <a name="keywords"></a>키워드

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- 여권 #
- 여권 #
- passportid
- passports
- passportno
- passport 아니요
- passportnumber
- 여권 번호
- passportnumbers
- 여권 번호

#### <a name="keywords_croatia_eu_passport_number"></a>Keywords_croatia_eu_passport_number

- broj putovnice
- br. Putovnice
- br putovnice
   
## <a name="croatia-personal-identification-oib-number"></a>크로아티아 OIB (개인 식별) 번호

### <a name="format"></a>형식일

11자리 숫자

### <a name="pattern"></a>패턴

11자리 숫자:
- 10 자리 숫자 
- 최종 숫자가 검사 숫자입니다.

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_croatia_oib_number 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keywords_croatia_eu_tax_file_number에서 키워드가 발견 되었습니다.
- 체크섬이 통과됩니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Func_croatia_oib_number 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- 체크섬이 통과됩니다.

```xml
      <!-- Croatia Personal Identification (OIB) Number -->
      <Entity id="31983b6d-db95-4eb2-a630-b44bd091968d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_oib_number" />
          <Match idRef="Keywords_croatia_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_oib_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_croatia_oib_number"></a>Keyword_croatia_oib_number

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

#### <a name="keywords_cyprus_eu_drivers_license_number"></a>Keywords_cyprus_eu_driver ' s_license_number

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


## <a name="cyprus-identity-card"></a>키프로스 id 카드
이 중요 한 정보 유형은 다음 에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거 버 넌 스
- 레코드 관리
- Microsoft cloud app security

### <a name="format"></a>형식일

공백과 구분 기호가 없는 10 자리 숫자
  
### <a name="pattern"></a>패턴

10 자리 숫자 
  
### <a name="checksum"></a>제외

해당 없음
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- 정규식이 해당  `Regex_cyprus_eu_national_id_card` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_cyprus_eu_national_id_card` 찾았습니다. 
    
```xml 
      <!-- Cyprus Identity Card -->
      <Entity id="3ba8afe5-7a6c-4929-8247-0001b6878438" patternsProximity="300" recommendedConfidence="75">
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
- From  `Keywords_eu_passport_number_common` 또는 found의 키워드 `Keywords_cyprus_eu_passport_number` 입니다. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_cyprus_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- 여권 #
- 여권 #
- passportid
- passports
- passportno
- passport 아니요
- passportnumber
- 여권 번호
- passportnumbers
- 여권 번호

#### <a name="keywords_cyprus_eu_passport_number"></a>Keywords_cyprus_eu_passport_number

- αριθμό διαβατηρίου
- pasaportu
- Αριθμός Διαβατηρίου
- κυπριακό διαβατήριο
- διαβατήριο #
- διαβατήριο
- αριθμός διαβατηρίου
- 고 aport Kimliği
- 고 aport numarası
- 고 aport 아니요
- Αρ. Διαβατηρίου

## <a name="cyprus-tax-identification-number"></a>키프로스 세금 식별 번호
이 중요 한 정보 유형은 다음 에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거 버 넌 스
- 레코드 관리
- Microsoft cloud app security

### <a name="format"></a>형식일

지정 된 패턴에서 8 자리 및 1 개 문자
  
### <a name="pattern"></a>패턴

8 자리 숫자와 1 개 문자:
  
- "0" 또는 "9"
- 7 자리 숫자
- 1 개 문자 (대/소문자 구분 안 함)
    
### <a name="checksum"></a>제외

해당 없음
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- 이 함수는 해당  `Func_cyprus_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_cyprus_eu_tax_file_number` 찾았습니다. 
    
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- 이 함수는 해당  `Func_cyprus_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
```xml
      <!-- Cyprus Tax Identification Number -->
      <Entity id="40e64bd9-55f3-4a09-9bd6-1db18dced9dd" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
          <Match idRef="Keywords_cyprus_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
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


## <a name="czech-drivers-license-number"></a>체코어 운전 면허 번호
이 중요 한 정보 유형 엔터티는 EU 드라이버의 라이선스 번호 중요 정보 유형 에서만 사용할 수 있습니다.

### <a name="format"></a>형식일

2 개의 문자 다음에 6 자리 숫자
  
### <a name="pattern"></a>패턴

8 개의 문자 및 숫자:
  
- 2 개 문자 (대/소문자 구분 안 함)
- 공백 (선택 사항)
- 6 자리 숫자

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

#### <a name="keywords_czech_republic_eu_drivers_license_number"></a>Keywords_czech_republic_eu_driver ' s_license_number

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
- From  `Keywords_eu_passport_number_common` 또는 found의 키워드 `Keywords_czech_republic_eu_passport_number` 입니다. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_czech_republic_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- 여권 #
- 여권 #
- passportid
- passports
- passportno
- passport 아니요
- passportnumber
- 여권 번호
- passportnumbers
- 여권 번호

#### <a name="keywords_czech_republic_eu_passport_number"></a>Keywords_czech_republic_eu_passport_number

- cestovní pas
- číslo (u)
- cestovní (u)
- 포트 번호 없음
- čísla (u)


## <a name="czech-personal-identity-number"></a>체코어 개인 id 번호

### <a name="format"></a>형식일

선택적 슬래시 (이전 형식)가 있는 9 자리 숫자와 슬래시 (새 형식)가 있는 10 자리 숫자

### <a name="pattern"></a>패턴

9 자리 숫자 (이전 형식):
- 출생 날짜를 나타내는 6 자리 숫자
- 선택적 슬래시
- 3 자리 숫자

10 자리 숫자 (새 형식):
- 출생 날짜를 나타내는 6 자리 숫자
- 선택적 슬래시 
- 마지막 숫자가 검사 숫자인 4 자리 숫자

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.

- Func_czech_id_card 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keyword_czech_id_card에서 키워드가 발견 되었습니다.
- 체크섬이 통과됩니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.

- Func_czech_id_card_new_format 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- 체크섬이 통과됩니다.

```xml
<!-- Czech Personal Identity Number -->
      <!-- Czech Personal Identity Number -->
      <Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_czech_id_card" />
          <Match idRef="Keyword_czech_id_card" />
        </Pattern>
        <Version minEngineVersion="15.20.3000.000">
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Func_czech_id_card_new_format" />
          </Pattern>
        </Version>
      </Entity>
```
### <a name="keywords"></a>키워드

#### <a name="keyword_czech_id_card"></a>Keyword_czech_id_card

- 돌 번호
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
- nationalnumber #
- 국가 번호
- osobní číslo
- personalidnumber #
- 개인 id 번호
- 개인 식별 번호
- 개인 번호
- 인 #
- 인
- pojištění číslo
- rč
- rodne cislo
- rodné číslo
- ssn
- ssn #
- 주민 등록 번호
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


## <a name="denmark-drivers-license-number"></a>덴마크 운전 면허 번호
이 중요 한 정보 유형 엔터티는 EU 드라이버의 라이선스 번호 중요 정보 유형 에서만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백과 구분 기호가 없는 8 자리 숫자
  
### <a name="pattern"></a>패턴

8 자리 숫자
  
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

#### <a name="keywords_denmark_eu_drivers_license_number"></a>Keywords_denmark_eu_driver ' s_license_number

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

9 자리 숫자 
  
### <a name="checksum"></a>제외

아니요
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- 정규식이 해당  `Regex_denmark_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From  `Keywords_eu_passport_number_common` 또는 found의 키워드 `Keywords_denmark_eu_passport_number` 입니다. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_denmark_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- 여권 #
- 여권 #
- passportid
- passports
- passportno
- passport 아니요
- passportnumber
- 여권 번호
- passportnumbers
- 여권 번호

#### <a name="keywords_denmark_eu_passport_number"></a>Keywords_denmark_eu_passport_number

- pasnummer
- 포트 n °
- 를 다시


## <a name="denmark-personal-identification-number"></a>덴마크 개인 식별 번호

### <a name="format"></a>형식일

하이픈을 포함 하는 10 자리 숫자

### <a name="pattern"></a>패턴

10 자리 숫자:
- 출생 날짜에 해당 하는 DDMMYY 형식의 6 자리 숫자 
- 하이픈 
- 마지막 숫자가 검사 숫자인 4 자리 숫자

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- 정규식 Func_denmark_eu_tax_file_number 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keyword_denmark_id에서 키워드가 발견 되었습니다.
- 체크섬이 통과됩니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 65% 신뢰합니다.
- 정규식 Func_denmark_eu_tax_file_number 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- 체크섬이 통과됩니다.

```xml
<!-- Denmark Personal Identification Number -->
      <!-- Denmark Personal Identification Number -->
      <Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
          <Match idRef="Keyword_denmark_id" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
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
- nationalnumber #
- 국가 번호
- personalidnumber #
- personalidentityno #
- 개인 id 번호
- personnummer
- personnummer #
- reisekrankenversicherungskartenummer
- rejsesygesikringskort
- ssn
- ssn #
- 번호 (|)
- kode
- nummer에서
- skattenummer
- 주민 등록 번호
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
- cpr.nr
- cprnr
- cprnummer
- personnr
- personregister
- sygesikringsbevis
- sygesikringsbevisnr
- sygesikringsbevisnummer
- sygesikringskort
- sygesikringskortnr
- sygesikringskortnummer
- sygesikringsnr
- sygesikringsnummer


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


## <a name="drug-enforcement-agency-dea-number"></a>DEA (약품 집행 기관) 번호

### <a name="format"></a>형식일

2 개 문자와 7 자리 숫자

### <a name="pattern"></a>패턴

패턴에는 다음이 모두 포함되어야 합니다.
- 이 가능한 문자 집합에서의 한 문자 (대/소문자 구분 안 함): abcdefghjklmnprstux (등록자 성의 코드) 
- 1 개의 문자 (대/소문자 구분 안 함), 등록자 성의 성의 첫 번째 문자 
- 검사 숫자의 마지막 7 자리 숫자

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
  
- 문자 "ET" (대/소문자 구분 안 함) 
- 6 자리 숫자
    
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

#### <a name="keywords_estonia_eu_drivers_license_number"></a>Keywords_estonia_eu_driver ' s_license_number

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


## <a name="estonia-personal-identification-code"></a>에스토니아 개인 식별 코드
이 중요 한 정보 유형은 다음 에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거 버 넌 스
- 레코드 관리
- Microsoft cloud app security

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
      <!-- Estonia Personal Identification Code -->
      <Entity id="bfb26de6-dad5-4d48-ab72-4789cdd0654c" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
          <Match idRef="Keywords_estonia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_estonia_eu_telephone_number" />
            <Match idRef="Keywords_estonia_eu_mobile_number" />
          </Any>
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
- From  `Keywords_eu_passport_number_common` 또는 found의 키워드 `Keywords_estonia_eu_passport_number` 입니다. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_estonia_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- 여권 #
- 여권 #
- passportid
- passports
- passportno
- passport 아니요
- passportnumber
- 여권 번호
- passportnumbers
- 여권 번호

#### <a name="keywords_estonia_eu_passport_number"></a>Keywords_estonia_eu_passport_number

eesti kodaniku pass si 번호 passinumbrid 문서 번호 문서에 dokumendi veiligheid

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
- [체코어](#czech-drivers-license-number)
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

- [오스트리아](#austria-identity-card)
- [벨기에](#belgium-national-number)
- [불가리아](#bulgaria-uniform-civil-number)
- [크로아티아](#croatia-identity-card-number)
- [키프로스](#cyprus-identity-card)
- [체코어](#czech-personal-identity-number)
- [덴마크](#denmark-personal-identification-number)
- [에스토니아](#estonia-personal-identification-code)
- [핀란드](#finland-national-id)
- [프랑스](#france-national-id-card-cni)
- [독일](#germany-identity-card-number)
- [그리스](#greece-national-id-card)
- [헝가리](#hungary-personal-identification-number)
- [아일랜드](#ireland-personal-public-service-pps-number)
- [이탈리아](#italy-fiscal-code)
- [라트비아](#latvia-personal-code)
- [리투아니아](#lithuania-personal-code)
- [셈](#luxemburg-national-identification-number-natural-persons)
- [몰타](#malta-identity-card-number)
- [네덜란드](#netherlands-citizens-service-bsn-number)
- [폴란드](#poland-national-id-pesel)
- [포르투갈](#portugal-citizen-card-number)
- [루마니아](#romania-personal-numeric-code-cnp)
- [슬로바키아](#slovakia-personal-number)
- [슬로베니아](#slovenia-unique-master-citizen-number)
- [스페인](#spain-dni)
- [영국](#uk-national-insurance-number-nino)                                        


## <a name="eu-passport-number"></a>EU 여권 번호 

이러한 엔터티는 EU 여권 번호 중요 한 정보 유형으로 서 EU 여권 번호 번들의 엔터티입니다.

- [오스트리아](#austria-passport-number)
- [벨기에](#belgium-passport-number)
- [불가리아](#bulgaria-passport-number)
- [크로아티아](#croatia-passport-number)
- [키프로스](#cyprus-passport-number)
- [체코어](#czech-passport-number)
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
- [체코어](#czech-social-security-number-or-equivalent-identification)
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

이러한 엔터티는 EU 세금 식별 번호 중요 정보 유형입니다.

- [오스트리아](#austria-tax-identification-number)
- [벨기에](#belgium-national-number)
- [불가리아](#bulgaria-uniform-civil-number)
- [크로아티아](#croatia-identity-card-number)
- [키프로스](#cyprus-tax-identification-number)
- [체코어](#czech-personal-identity-number)
- [덴마크](#denmark-personal-identification-number)
- [에스토니아](#estonia-personal-identification-code)
- [핀란드](#finland-national-id)
- [프랑스](#france-tax-identification-number)
- [독일](#germany-tax-identification-number)
- [그리스](#greece-tax-identification-number)
- [헝가리](#hungary-tax-identification-number)
- [아일랜드](#ireland-personal-public-service-pps-number)
- [이탈리아](#italy-fiscal-code)
- [라트비아](#latvia-personal-code)
- [리투아니아](#lithuania-personal-code)
- [셈](#luxemburg-national-identification-number-non-natural-persons)
- [몰타](#malta-tax-identification-number)
- [네덜란드](#netherlands-tax-identification-number)
- [폴란드](#poland-tax-identification-number)
- [포르투갈](#portugal-tax-identification-number)
- [루마니아](#romania-personal-numeric-code-cnp)
- [슬로바키아](#slovakia-personal-number)
- [슬로베니아](#slovenia-tax-identification-number)
- [스페인](#spain-tax-identification-number)
- [스웨덴](#sweden-tax-identification-number)
- [영국](#uk-unique-taxpayer-reference-number)


## <a name="finland-drivers-license-number"></a>핀란드 운전 면허 번호
이 중요 한 정보 유형 엔터티는 EU 드라이버의 라이선스 번호 중요 정보 유형 에서만 사용할 수 있습니다.

### <a name="format"></a>형식일

하이픈을 포함 하는 10 자리 숫자
  
### <a name="pattern"></a>패턴

하이픈을 포함 하는 10 자리 숫자:
  
- 6 자리 숫자 
- 하이픈
- 4 자리 숫자 
    
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

#### <a name="keywords_finland_eu_drivers_license_number"></a>Keywords_finland_eu_driver ' s_license_number

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


## <a name="finland-european-health-insurance-number"></a>핀란드 유럽 건강 보험 번호
이 중요 한 정보 유형은 다음 에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거 버 넌 스
- 레코드 관리
- Microsoft cloud app security

### <a name="format"></a>형식일

20 자리 숫자

### <a name="pattern"></a>패턴

20 자리 숫자:

- 10 자리 숫자-8024680246
- 선택적 공백 또는 하이픈
- 10 자리 숫자

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Regex Regex_Finland_European_Health_Insurance_Number는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keyword_Finland_European_Health_Insurance_Number에서 키워드가 발견 되었습니다.

```xml
      <!-- Finland European Health Insurance Number -->
      <Entity id="60f75aed-81bf-4625-89b0-0846b9248ee7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Finland_European_Health_Insurance_Number"/>
          <Match idRef="Keyword_Finland_European_Health_Insurance_Number"/>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>키워드

#### <a name="keyword_finland_european_health_insurance_number"></a>Keyword_finland_european_health_insurance_number

- ehic #
- ehic
- finlandehicnumber #
- finsjukförsäkringskort a
- 건강 카드
- 건강 보험 카드
- 건강 보험 번호
- hälsokort
- sairaanhoitokortin
- sairausvakuutuskortti
- sairausvakuutusnumero
- sjukförsäkring nummer
- sjukförsäkringskort
- suomen sairausvakuutuskortti
- terveyskortti


## <a name="finland-national-id"></a>핀란드 국가 ID

### <a name="format"></a>형식일

6 자리 숫자와 세기를 나타내는 문자 및 3 자리 숫자와 검사 숫자

### <a name="pattern"></a>패턴

패턴에는 다음이 모두 포함되어야 합니다.
- 생년월일에 해당 하는 DDMMYY 형식의 6 자리 숫자 
- 세기 표식 ('-', ' + ' 또는 ' a ') 
- 3 자리 개인 식별 번호 
- 검사 숫자에 해당 하는 숫자 또는 문자 (대/소문자 구분 안 함)

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_finnish_national_id 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keyword_finnish_national_id에서 키워드를 찾음
- 체크섬 통과

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Func_finnish_national_id 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- 체크섬 통과

```xml
      <!-- Finnish National ID-->
      <Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finnish_national_id" />
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
- 주민 등록 번호
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
9 개의 문자 및 숫자 조합

### <a name="pattern"></a>패턴
9 개의 문자와 숫자를 조합한 것입니다.
- 2 개 문자 (대/소문자 구분 안 함) 
- 7 자리 숫자

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- 정규식 Regex_finland_passport_number 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keywords_eu_passport_number_common 또는 Keyword_finland_passport_number의 키워드를 찾았습니다.

```xml
<!-- Finland Passport Number -->
<Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keyword_finland_passport_number" />
          </Any>
        </Pattern>
</Entity>
```
### <a name="keywords"></a>키워드

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- 여권 #
- 여권 #
- passportid
- passports
- passportno
- passport 아니요
- passportnumber
- 여권 번호
- passportnumbers
- 여권 번호

#### <a name="keyword_finland_passport_number"></a>Keyword_finland_passport_number

- suomalainen (si)
- passin numero
- passin numero. #
- passin numero #
- passin numero.
- 에이 si #
- 값


## <a name="finland-social-security-number-or-equivalent-identification"></a>핀란드 주민 등록 번호 또는 동등한 식별
이 중요 한 정보 유형 엔터티는 EU 주민 등록 번호 또는 해당 ID 중요 정보 유형에 서만 사용할 수 있습니다.

### <a name="format"></a>형식일

지정 된 형식의 11 자 조합
  
### <a name="pattern"></a>패턴

다음은 지정 된 형식의 11 자 조합입니다.
  
- 6 자리 숫자 
- 다음 중 하나의 인스턴스에 대해 다음을 수행 합니다.
  - 더하기 기호
  - 빼기 기호
  - 문자 "A" (대/소문자 구분 안 함)
- 3 자리 숫자
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
- Func_french_drivers_license 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- 다음 중 하나 이상이 충족 됩니다.
- Keyword_french_drivers_license에서 키워드가 발견 되었습니다.
- Func_eu_date 함수는 올바른 날짜 형식의 날짜를 찾습니다.

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


## <a name="france-health-insurance-number"></a>프랑스 건강 보험 번호
이 중요 한 정보 유형은 다음 에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거 버 넌 스
- 레코드 관리
- Microsoft cloud app security

### <a name="format"></a>형식일

21 자리 숫자

### <a name="pattern"></a>패턴

21 자리 숫자:

- 10 자리 숫자
- 선택적 공백
- 10 자리 숫자
- 선택적 공백
- 숫자


### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- regex Regex_France_Health_Insurance_Number는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keyword_France_Health_Insurance_Number에서 키워드가 발견 되었습니다.

```xml
      <!-- France Health Insurance Number -->
      <Entity id="9bc2069e-76df-4ff9-ac02-2f519469e236" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_France_Health_Insurance_Number"/>
          <Match idRef="Keyword_France_Health_Insurance_Number"/>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>키워드

#### <a name="keyword_france_health_insurance_number"></a>Keyword_France_health_insurance_number

- 보험 카드
- carte vitale
- carte d'assuré social


## <a name="france-national-id-card-cni"></a>프랑스 국가 id 카드 (CNI)

### <a name="format"></a>형식일

12자리 숫자

### <a name="pattern"></a>패턴

12자리 숫자

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 65% 신뢰합니다.
- Regex_france_cni 정규식이 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keywords_france_eu_national_id_card에서 키워드가 발견 되었습니다.

```xml
    <!-- France CNI -->
    <Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
        <Match idRef="Keywords_france_eu_national_id_card" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_france_eu_national_id_card"></a>Keywords_france_eu_national_id_card

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

9 자리 숫자 및 문자

### <a name="pattern"></a>패턴

9 자리 숫자 및 문자:
- 2 자리 숫자 
- 2 개 문자 (대/소문자 구분 안 함) 
- 5 자리 숫자

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

### <a name="format"></a>형식일

13자리 숫자
  
### <a name="pattern"></a>패턴

13자리 숫자
  
- 0, 1, 2 또는 3 이어야 하는 1 자리 숫자
- 1 자리 숫자
- 공백 1개(선택 사항)
- 2 자리 숫자 
- 공백 1개(선택 사항)
- 3 자리 숫자 
- 공백 1개(선택 사항)
- 3 자리 숫자 
- 공백 1개(선택 사항)
- 3 개의 검사 숫자 

  
### <a name="checksum"></a>제외

예
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- 이 함수는 해당  `Func_france_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_france_eu_tax_file_number` 찾았습니다. 
    
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- 이 함수는 해당  `Func_france_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
```xml
      <!-- France Tax Identification Number (numéro SPI.) -->
      <Entity id="ed59e77e-171d-442c-9ec1-88e2ebcb5b0a" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
          <Match idRef="Keywords_france_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_france_eu_telephone_number" />
            <Match idRef="Keywords_france_eu_mobile_number" />
          </Any>
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


## <a name="france-value-added-tax-number"></a>프랑스 값 추가 된 세금 번호
이 중요 한 정보 유형은 다음 에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거 버 넌 스
- 레코드 관리
- Microsoft cloud app security

### <a name="format"></a>형식일

13 문자 영숫자 패턴

### <a name="pattern"></a>패턴

13 문자 영숫자 패턴:

- 두 개의 문자-FR (대/소문자 구분 안 함)
- 선택적 공백 또는 하이픈
- 두 개의 문자 또는 숫자
- 선택적 공백, 점, 하이픈 또는 쉼표
- 3 자리 숫자
- 선택적 공백, 점, 하이픈 또는 쉼표
- 3 자리 숫자
- 선택적 공백, 점, 하이픈 또는 쉼표
- 3 자리 숫자

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_france_value_added_tax_number 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keywords_france_value_added_tax_number에서 키워드가 발견 되었습니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Func_france_value_added_tax_number 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.

```xml
      <!-- France Value Added Tax Number -->
      <Entity id="949121e6-ad9f-4379-8731-710342baea78" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_france_value_added_tax_number" />
          <Match idRef="Keywords_france_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_france_value_added_tax_number" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>키워드

#### <a name="keyword_france_value_added_tax_number"></a>Keyword_France_value_added_tax_number

- vat 번호
- vat 아니요
- vat #
- 부가 세금
- siren id 없음 numéro d'identification taxe sur siren ajoutée
- taxe valeur ajoutée
- taxe sur la valeur ajoutée
- n ° tva
- numéro de
- numéro d'identification siren


## <a name="germany-drivers-license-number"></a>독일 운전 면허 번호
이 중요 한 정보 유형 엔터티는 EU 드라이버의 라이선스 번호 중요 한 정보 유형에 포함 되며 독립 실행형 중요 한 정보 유형 엔터티로 사용할 수 있습니다.

### <a name="format"></a>형식일

11 자리 숫자와 문자 조합

### <a name="pattern"></a>패턴

11자리 숫자와 문자(대/소문자 구분 안 함):
- 숫자 또는 문자 
- 2 자리 숫자 
- 6 자리 숫자 또는 문자 
- 숫자 
- 숫자 또는 문자

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

- Nr-Führerschein 
- Nr-Fuhrerschein 
- Nr-Fuehrerschein 
- No-Führerschein 
- No-Fuhrerschein 
- No-Fuehrerschein 
- N-Führerschein 
- N-Fuhrerschein 
- N-Fuehrerschein
- Nr-Führerschein 
- Nr-Fuhrerschein 
- Nr-Fuehrerschein 
- No-Führerschein 
- No-Fuhrerschein 
- No-Fuehrerschein 
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

### <a name="format"></a>형식일

2010 년 11 월 1 일 이후: 9 개 문자 및 숫자

1 월 1987 년 10 월 31 일 (2010:10 자리 숫자)

### <a name="pattern"></a>패턴

2010 년 11 월 1 일 이후:
- 1 개 문자 (대/소문자 구분 안 함) 
- 8 자리 숫자

1 년 4 월 1987 일 ~ 10 2010 월 31 일까 지:
- 10 자리 숫자

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

10 자리 숫자 또는 문자

### <a name="pattern"></a>패턴

패턴에는 다음이 모두 포함되어야 합니다.
- 첫 번째 문자는 숫자 또는이 집합의 문자 (C, F, G, H, J, K)입니다. 
- 3 자리 숫자 
- 이 집합의 5 자리 숫자 또는 문자 (C,-H, J-N, P, R, T, V-Z) 
- 숫자

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_german_passport 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- From 키워드를 `Keyword_german_passport` 찾았습니다.
- 체크섬이 통과됩니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Func_german_passport_data 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- From 키워드를 `Keyword_german_passport` 찾았습니다.
- 체크섬이 통과됩니다.

```xml
    <!-- German Passport Number -->
    <Entity id="2e3da144-d42b-47ed-b123-fbf78604e52c" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_german_passport" />
        <Match idRef="Keyword_german_passport" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_passport_data" />
        <Match idRef="Keyword_german_passport" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_german_passport"></a>Keyword_german_passport

- reisepasse
- reisepassnummer
- No-Reisepass 
- Nr-Reisepass
- Reisepass-Nr
- Passnummer
- reisepässe
- 포트 번호입니다.
- 포트 번호 없음

## <a name="germany-tax-identification-number"></a>독일 세금 식별 번호

### <a name="format"></a>형식일

공백과 구분 기호를 사용 하지 않고 11 자리 숫자
  
### <a name="pattern"></a>패턴

11 자리 숫자:
  
- 2자리 숫자 
- 선택적 공백 1개
- 3자리 숫자 
- 선택적 공백 1개
- 3자리 숫자 
- 선택적 공백 1개
- 2자리 숫자
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
      <!-- Germany Tax Identification Number -->
      <Entity id="43316a89-9880-40cf-b980-04bc7eefcec5" patternsProximity="300" recommendedConfidence="85">
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


## <a name="germany-value-added-tax-number"></a>독일 값 세금 번호 추가 됨
이 중요 한 정보 유형은 다음 에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거 버 넌 스
- 레코드 관리
- Microsoft cloud app security

### <a name="format"></a>형식일

11 문자 영숫자 패턴

### <a name="pattern"></a>패턴

11 자리 영숫자 패턴:

- 문자 D 또는 d
- 문자 E 또는 e
- 선택적 공백
- 3 자리 숫자
- 선택적 공백 또는 쉼표
- 3 자리 숫자
- 선택적 공백 또는 쉼표
- 3 자리 숫자

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_germany_value_added_tax_number 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keywords_germany_value_added_tax_number에서 키워드가 발견 되었습니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Func_germany_value_added_tax_number 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.

```xml
      <!-- Germany Value Added Tax Number -->
      <Entity id="db177eb2-8811-4842-bffc-128c14aa219f" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_germany_value_added_tax_number" />
          <Match idRef="Keywords_germany_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_germany_value_added_tax_number" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>키워드

#### <a name="keyword_germany_value_added_tax_number"></a>Keyword_germany_value_added_tax_number

- vat 번호
- vat 아니요
- vat #
- vat # mehrwertsteuer
- mwst
- mehrwertsteuer identifikationsnummer
- mehrwertsteuer nummer


## <a name="greece-drivers-license-number"></a>그리스 운전 면허 번호
이 중요 한 정보 유형 엔터티는 EU 드라이버의 라이선스 번호 중요 한 정보 유형에 포함 되며 독립 실행형 중요 한 정보 유형 엔터티로 사용할 수 있습니다.

### <a name="format"></a>형식일

공백과 구분 기호를 사용 하지 않고 9 자리 숫자
  
### <a name="pattern"></a>패턴

9 자리 숫자 
  
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

#### <a name="keywords_greece_eu_drivers_license_number"></a>Keywords_greece_eu_driver ' s_license_number

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

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 65% 신뢰합니다.
- 정규식 Regex_greece_id_card 해당 패턴과 일치 하는 콘텐츠를 찾습니다.

```xml
      <!-- Greece National ID Card -->
      <Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_greece_id_card" />
          <Match idRef="Keyword_greece_id_card" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_greece_id_card" />
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
- From  `Keywords_eu_passport_number_common` 또는 found의 키워드 `Keywords_greece_eu_passport_number` 입니다. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_greece_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- 여권 #
- 여권 #
- passportid
- passports
- passportno
- passport 아니요
- passportnumber
- 여권 번호
- passportnumbers
- 여권 번호

#### <a name="keywords_greece_eu_passport_number"></a>Keywords_greece_eu_passport_number

- αριθμός διαβατηρίου
- αριθμούς διαβατηρίου
- αριθμός διαβατηριο

## <a name="greece-tax-identification-number"></a>그리스 세금 식별 번호
이 중요 한 정보 유형은 다음 에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거 버 넌 스
- 레코드 관리
- Microsoft cloud app security

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
    
```xml
      <!-- Greek Tax Identification Number -->
      <Entity id="15a54a5a-53d4-4080-ad43-a2a4fe1d3bf7" patternsProximity="300" recommendedConfidence="75">
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

#### <a name="keywords_hungary_eu_drivers_license_number"></a>Keywords_hungary_eu_driver ' s_license_number

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


## <a name="hungary-personal-identification-number"></a>헝가리어 개인 식별 번호
이 중요 한 정보 유형은 다음 에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거 버 넌 스
- 레코드 관리
- Microsoft cloud app security

### <a name="format"></a>형식일

11자리 숫자
  
### <a name="pattern"></a>패턴

11자리 숫자:
  
- 성별에 해당 하는 1 자리 숫자 (1gb, 2 암, 기타 번호는 두 개를 포함 하는 경우 1900에만 발생 합니다. 
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
      <!-- Hungary Personal Identification Number -->
      <Entity id="7b5cc218-7046-47d9-80c9-f325b50896ca" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
          <Match idRef="Keywords_hungary_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_hungary_eu_telephone_number" />
            <Match idRef="Keywords_hungary_eu_mobile_number" />
          </Any>
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
- From  `Keywords_eu_passport_number_common` 또는 found의 키워드 `Keywords_hungary_eu_passport_number` 입니다. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_hungary_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```
### <a name="keywords"></a>키워드

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- 여권 #
- 여권 #
- passportid
- passports
- passportno
- passport 아니요
- passportnumber
- 여권 번호
- passportnumbers
- 여권 번호

#### <a name="keywords_hungary_eu_passport_number"></a>Keywords_hungary_eu_passport_number

- útlevél száma
- Útlevelek száma
- útlevél szám

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
이 중요 한 정보 유형은 다음 에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거 버 넌 스
- 레코드 관리
- Microsoft cloud app security

### <a name="format"></a>형식일

공백이 나 구분 기호가 없는 10 자리 숫자
  
### <a name="pattern"></a>패턴

10 자리 숫자:
  
- "8" 이어야 하는 1 자리 숫자 
- 8자리 숫자
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
      <!-- Hungary Tax Identification Number -->
      <Entity id="ede42eb4-59d9-49eb-9603-d7853fbda91d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
          <Match idRef="Keywords_hungary_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_hungary_eu_telephone_number" />
            <Match idRef="Keywords_hungary_eu_mobile_number" />
          </Any>
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


## <a name="hungary-value-added-tax-number"></a>헝가리 값 추가 된 세금 번호
이 중요 한 정보 유형은 다음 에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거 버 넌 스
- 레코드 관리
- Microsoft cloud app security

### <a name="format"></a>형식일

10 문자 영숫자 패턴

### <a name="pattern"></a>패턴

10 자리 영숫자 패턴:

- 2 개의 문자-HU 또는 HU
- 선택적 공간
- 8 자리 숫자

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.

- Func_hungarian_value_added_tax_number 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keywords_hungarian_value_added_tax_number에서 키워드가 발견 되었습니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.

- Func_hungarian_value_added_tax_number 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.

```xml
      <!-- Hungarian Value Added Tax Number -->
      <Entity id="976349a0-683b-477a-90f8-ff0a220d5592" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungarian_value_added_tax_number" />
          <Match idRef="Keywords_hungarian_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungarian_value_added_tax_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_hungary_value_added_tax_number"></a>Keyword_Hungary_value_added_tax_number

- vat
- 값이 추가 된 세금 번호
- vat #
- vatno #
- hungarianvatno #
- 세금 번호
- 부가 세금 áfa
- közösségi adószám
- általános forgalmi adó
- hozzáadottérték adó
- áfa szám


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

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_india_aadhaar 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keyword_india_aadhar에서 키워드가 발견 되었습니다.
- 체크섬이 통과됩니다.
- 
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.

- Func_india_aadhaar 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- 체크섬이 통과됩니다.

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

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.

- 정규식 Regex_indonesia_id_card 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keyword_indonesia_id_card에서 키워드가 발견 되었습니다.

```xml
<!-- Indonesia Identity Card (KTP) Number -->
<Entity id="da68fdb0-f383-4981-8c86-82689d3b7d55" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_indonesia_id_card"/>
     <Match idRef="Keyword_indonesia_id_card"/>
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

ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, to, do, ee, es, fi,,, fr, gb, ge, gi, gl, gr, hr, hu, kw, il, vg,, nl-nl, tn,,,,,,,,, ,,,,,,,,,,,,, rs, l, se, si,

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

### <a name="keywords"></a>키워드

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

#### <a name="keywords_ireland_eu_drivers_license_number"></a>Keywords_ireland_eu_driver ' s_license_number

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
- From  `Keywords_eu_passport_number_common` 또는 found의 키워드 `Keywords_ireland_eu_passport_number` 입니다. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_ireland_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- 여권 #
- 여권 #
- passportid
- passports
- passportno
- passport 아니요
- passportnumber
- 여권 번호
- passportnumbers
- 여권 번호

#### <a name="keywords_ireland_eu_passport_number"></a>Keywords_ireland_eu_passport_number

- 포트 numero
- uimhreacha pasanna
- uimhir pas
- uimhir phas
- uimhreacha pas
- uimhir cárta
- uimhir chárta

## <a name="ireland-personal-public-service-pps-number"></a>아일랜드 PPS (개인 공개 서비스) 번호

### <a name="format"></a>형식일

이전 형식 (31 년 12 월 2012 일까지):
- 7 자리 숫자와 1-2 자 

새 형식 (1 년 1 월 2013 및 이후):
- 7 자리 숫자와 2 개 문자

### <a name="pattern"></a>패턴

이전 형식 (31 년 12 월 2012 일까지):
- 7 자리 숫자 
- 1 ~ 2 개 문자 (대/소문자 구분 안 함) 

새 형식 (1 년 1 월 2013 및 이후):
- 7 자리 숫자 
- 알파벳 검사 숫자에 해당 하는 문자 (대/소문자 구분 안 함)입니다. 
- A-I 범위의 선택적 문자 또는 "W"

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_ireland_pps 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keywords_ireland_eu_national_id_card에서 키워드가 발견 되었습니다.
- 체크섬이 통과됩니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 65% 신뢰합니다.
- Func_ireland_pps 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- 체크섬이 통과됩니다.

```xml
      <!-- Ireland Personal Public Service (PPS) Number -->
      <Entity id="1cdb674d-c19a-4fcf-9f4b-7f56cc87345a" patternsProximity="300" recommendedConfidence="85" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_pps" />
          <Match idRef="Keywords_ireland_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_ireland_pps" />
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
- pps 번호
- pps 서비스 없음
- ppsn
- ppsno #
- ppsno
- psp
- 공용 서비스 없음
- publicserviceno #
- publicserviceno
- 수입 및 주민 등록 보험 번호
- rsi 아니요
- rsi 번호
- rsin
- seirbhís aitheantais client
- uimh
- uimhir aitheantais chánach
- uimhir aitheantais phearsanta
- uimhir phearsanta seirbhíse poiblí
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


## <a name="israel-bank-account-number"></a>이스라엘 은행 계좌 번호

### <a name="format"></a>형식일

13자리 숫자

### <a name="pattern"></a>패턴

서식이
- 2 자리 숫자 
- 대시 
- 3 자리 숫자 
- 대시 
- 8 자리 숫자

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

9 자리 숫자

### <a name="pattern"></a>패턴

9 자리 연속 숫자

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

10 개의 문자 및 숫자 조합

### <a name="pattern"></a>패턴

- 10 개의 문자와 숫자를 조합한 것입니다.
- 1 개 문자 (대/소문자 구분 안 함) 
- 문자 "A" 또는 "V" (대/소문자 구분 안 함) 
- 7 개 문자 (대/소문자 구분 안 함), 숫자 또는 밑줄 문자 
- 1 개 문자 (대/소문자 구분 안 함)

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

## <a name="italy-fiscal-code"></a>이탈리아 회계 코드
이 중요 한 정보 유형은 다음 에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거 버 넌 스
- 레코드 관리
- Microsoft cloud app security

### <a name="format"></a>형식일

지정 된 패턴에 해당 하는 문자 및 숫자의 16 자 조합
  
### <a name="pattern"></a>패턴

문자와 숫자의 16 자 조합:
- 가족 이름에서 처음 세 개의 자음에 해당 하는 3 개의 문자
- 이름의 첫 번째, 세 번째 및 네 번째 자음에 해당 하는 3 개의 문자
- 출생 연도의 마지막 자리에 해당 하는 2 자리 숫자
- 출생 월의 문자에 해당 하는 한 문자는 알파벳 순서로 사용 되지만 1 ~ E, H, L, M, P, R에 해당 하는 문자를 사용 하는 경우에만 사용할 수 있습니다.
- genders를 구분 하기 위해 출생 달의 날짜에 해당 하는 2 자리 숫자 (40)가 여성 생년월일에 추가 되었습니다.
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
      <!-- Italy Fiscal Code -->
      <Entity id="4cd79172-8da9-4ff5-9188-98b1e7e2eca6" patternsProximity="300" recommendedConfidence="85">
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
  
- 2 자리 숫자 또는 문자 (대/소문자 구분 안 함)
- 7 자리 숫자
    
### <a name="checksum"></a>제외

해당 없음
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- 정규식이 해당  `Regex_italy_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From  `Keywords_eu_passport_number_common` 또는 found의 키워드 `Keywords_italy_eu_passport_number` 입니다. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_italy_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- 여권 #
- 여권 #
- passportid
- passports
- passportno
- passport 아니요
- passportnumber
- 여권 번호
- passportnumbers
- 여권 번호

#### <a name="keywords_italy_eu_passport_number"></a>Keywords_italy_eu_passport_number

- italiana passaporto
- passaporto italiana
- passaporto numero
- numéro (고) 포트
- numero di passaporto
- numeri del passaporto
- 포트 italien

## <a name="italy-value-added-tax-number"></a>이탈리아 값 세금 번호 추가
이 중요 한 정보 유형은 다음 에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거 버 넌 스
- 레코드 관리
- Microsoft cloud app security

### <a name="format"></a>형식일

선택적 구분 기호가 있는 13 자리 영숫자 패턴

### <a name="pattern"></a>패턴

선택적 구분 기호가 있는 13 자리 영숫자 패턴:

- I 또는 i
- T 또는 t
- 선택적 공백, 점, 하이픈 또는 쉼표
- 11자리 숫자

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_italy_value_added_tax_number 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keywords_italy_value_added_tax_number에서 키워드가 발견 되었습니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Func_italy_value_added_tax_number 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.

```xml
      <!-- Italy Value Added Tax -->
      <Entity id="26a8cc07-2283-4a2a-ab1d-4ab643c4c67f" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_value_added_tax_number" />
          <Match idRef="Keywords_italy_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_value_added_tax_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_italy_value_added_tax_number"></a>Keyword_italy_value_added_tax_number

- vat 번호
- vat 아니요
- vat #
- iva
- iva #


## <a name="japan-bank-account-number"></a>일본 은행 계좌 번호

### <a name="format"></a>형식일

7 또는 8 자리 숫자

### <a name="pattern"></a>패턴

은행 계좌 번호:
- 7 또는 8 자리 숫자
- 은행 계좌 분기 코드:
- 4 자리 숫자 
- 공백 또는 대시 (선택 사항) 
- 3 자리 숫자

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


## <a name="japan-my-number---corporate"></a>일본 내 번호-회사
이 중요 한 정보 유형은 다음 에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거 버 넌 스
- 레코드 관리
- Microsoft cloud app security

### <a name="format"></a>형식일

13 자리 숫자

### <a name="pattern"></a>패턴

13 자리 숫자:

- 1 ~ 9 자리 숫자
- 12자리 숫자

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_japanese_my_number_corporate 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keywords_japanese_my_number_corporate에서 키워드가 발견 되었습니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Func_japanese_my_number_corporate 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.

```xml
      <!-- Japanese My Number – Corporate -->
      <Entity id="9e0eaf79-ff20-4ffb-b3e4-e7368d5db6ff" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_japanese_my_number_corporate" />
          <Match idRef="Keywords_japanese_my_number_corporate" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_japanese_my_number_corporate" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_japan_my_number_corporate"></a>Keyword_japan_my_number_corporate

- 회사 번호
- マイナンバー
- 共通番号
- マイナンバーカード
- マイナンバーカード番号
- 個人番号カード
- 個人識別番号
- 個人識別ナンバー
- 法人番号
- 指定通知書


## <a name="japan-my-number---personal"></a>일본 내 번호-개인
이 중요 한 정보 유형은 다음 에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거 버 넌 스
- 레코드 관리
- Microsoft cloud app security

### <a name="format"></a>형식일

12 자리 숫자

### <a name="pattern"></a>패턴

12 자리 숫자:

- 4 자리 숫자
- 선택적 공백, 점 또는 하이픈
- 4 자리 숫자
- 선택적 공백, 점 또는 하이픈
- 4 자리 숫자

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_japanese_my_number_personal 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keywords_japanese_my_number_personal에서 키워드가 발견 되었습니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 65% 신뢰합니다.
- Func_japanese_my_number_personal 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.

```xml
      <!-- Japanese My Number – Personal -->
      <Entity id="98da8e66-7299-4ebd-9f82-c871ab37d3ef" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_japanese_my_number_personal" />
          <Match idRef="Keywords_japanese_my_number_personal" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_japanese_my_number_personal" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_japan_my_number_personal"></a>Keyword_japan_my_number_personal

- 내 번호
- マイナンバー
- 個人番号
- 共通番号
- マイナンバーカード
- マイナンバーカード番号
- 個人番号カード
- 個人識別番号
- 個人識別ナンバー
- 通知カード

   
## <a name="japan-passport-number"></a>일본 여권 번호

### <a name="format"></a>형식일

2 개 문자와 7 자리 숫자

### <a name="pattern"></a>패턴

2 개의 문자 (대/소문자 구분 안 함)와 7 자리 숫자

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
- 2 개 문자 (대/소문자 구분 안 함)
- 8 자리 숫자 
- 2 개 문자 (대/소문자 구분 안 함)

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
- 4 자리 숫자 
- 하이픈 (선택 사항) 
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
  
- 3 개 문자 (대/소문자 구분 안 함) 
- 6 자리 숫자
    
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

#### <a name="keywords_latvia_eu_drivers_license_number"></a>Keywords_latvia_eu_driver ' s_license_number

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

## <a name="latvia-personal-code"></a>라트비아 개인 코드

### <a name="format"></a>형식일

11 자리 숫자와 선택적 하이픈
  
### <a name="pattern"></a>패턴

이전 형식

11 자리 숫자와 하이픈:
  
- 생년월일에 해당 하는 6 자리 숫자 (DDMMYY) 
- 하이픈
- 출생 세기에 해당 하는 1 자리 숫자 (19th 세기의 경우 "1", 21 세기의 경우 "2")
- 임의로 생성 되는 4 자리 숫자

새 형식

11자리 숫자

- 두 자리 숫자 "32"
- 9자리 숫자
    
### <a name="checksum"></a>제외

예
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Function  `Func_latvia_eu_national_id_card` 또는 regex에서 `Regex_latvia_eu_national_id_card_new_format` 해당 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_latvia_eu_national_id_card` 찾았습니다. 
    
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Function  `Func_latvia_eu_national_id_card` 또는 regex에서 `Regex_latvia_eu_national_id_card_new_format` 해당 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
```xml
      <!-- Latvia Personal Code -->
      <Entity id="03fcf763-27c2-49ed-9422-2641c6c895c9" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
          <Match idRef="Keywords_latvia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_latvia_eu_telephone_number" />
            <Match idRef="Keywords_latvia_eu_mobile_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_latvia_eu_national_id_card_new_format" />
          <Match idRef="Keywords_latvia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_national_id_card_new_format" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_latvia_eu_telephone_number" />
            <Match idRef="Keywords_latvia_eu_mobile_number" />
          </Any>
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
- 주민 등록 번호
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
  
- 2 자리 숫자 또는 문자 (대/소문자 구분 안 함)
- 7 자리 숫자
    
### <a name="checksum"></a>제외

아니요
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- 정규식이 해당  `Regex_latvia_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From  `Keywords_eu_passport_number_common` 또는 found의 키워드 `Keywords_latvia_eu_passport_number` 입니다. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_latvia_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- 여권 #
- 여권 #
- passportid
- passports
- passportno
- passport 아니요
- passportnumber
- 여권 번호
- passportnumbers
- 여권 번호

#### <a name="keywords_latvia_eu_passport_number"></a>Keywords_latvia_eu_passport_number

- pase numurs
- pase numur
- 고가을 numuri
- veiligheid es
- 포트 번호 없음
- n ° du 이상 Seport

## <a name="lithuania-drivers-license-number"></a>리투아니아 운전 면허 번호
이 중요 한 정보 유형 엔터티는 EU 드라이버의 라이선스 번호 중요 정보 유형 에서만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백과 구분 기호가 없는 8 자리 숫자
  
### <a name="pattern"></a>패턴

8 자리 숫자 
  
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

#### <a name="keywords_lithuania_eu_drivers_license_number"></a>Keywords_lithuania_eu_driver ' s_license_number

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

## <a name="lithuania-personal-code"></a>리투아니아 개인 코드
이 중요 한 정보 유형은 다음 에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거 버 넌 스
- 레코드 관리
- Microsoft cloud app security

### <a name="format"></a>형식일

공백과 구분 기호를 사용 하지 않고 11 자리 숫자
  
### <a name="pattern"></a>패턴

공백과 구분 기호를 사용 하지 않고 11 자리 숫자:
  
- 사용자의 성별 및 출생 세기에 해당 하는 1 자리 (1-6)
- 생년월일에 해당 하는 6 자리 숫자 (YYMMDD) 
- 출생 날짜의 일련 번호에 해당 하는 3 자리 숫자
- 검사 숫자 1 개
    
### <a name="checksum"></a>제외

예
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- 이 함수는 해당  `Func_lithuania_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_lithuania_eu_tax_file_number` 찾았습니다. 
    
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- 이 함수는 해당  `Func_lithuania_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
```xml
      <!-- Lithuania Personal Code -->
      <Entity id="cd6d3786-8ec3-4524-a2cf-1e0095379171" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
          <Match idRef="Keywords_lithuania_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_lithuania_eu_telephone_number" />
            <Match idRef="Keywords_lithuania_eu_mobile_number" />
          </Any>
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

해당 없음
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- 정규식이 해당  `Regex_lithuania_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From  `Keywords_eu_passport_number_common` 또는 found의 키워드 `Keywords_lithuania_eu_passport_number` 입니다. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_lithuania_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- 여권 #
- 여권 #
- passportid
- passports
- passportno
- passport 아니요
- passportnumber
- 여권 번호
- passportnumbers
- 여권 번호

#### <a name="keywords_lithuania_eu_passport_number"></a>Keywords_lithuania_eu_passport_number

- numeris
- #
- veiligheid

## <a name="luxemburg-drivers-license-number"></a>룩셈부르크 운전 면허 번호
이 중요 한 정보 유형 엔터티는 EU 드라이버의 라이선스 번호 중요 정보 유형 에서만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백과 구분 기호가 없는 6 자리 숫자
  
### <a name="pattern"></a>패턴

6 자리 숫자 
  
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

#### <a name="keywords_luxemburg_eu_drivers_license_number"></a>Keywords_luxemburg_eu_driver ' s_license_number

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

## <a name="luxemburg-national-identification-number-natural-persons"></a>룩셈부르크 국내 식별 번호 (자연어)
이 중요 한 정보 유형은 다음 에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거 버 넌 스
- 레코드 관리
- Microsoft cloud app security

### <a name="format"></a>형식일

공백이 나 구분 기호가 없는 13 자리 숫자
  
### <a name="pattern"></a>패턴

13자리 숫자:
  
- 11자리 숫자 
- 두 개의 검사 숫자
    
### <a name="checksum"></a>제외

예
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- 이 함수는 해당  `Func_luxemburg_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_luxemburg_eu_national_id_card` 찾았습니다. 

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- 이 함수는 해당  `Func_luxemburg_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 


```xml
      <!-- Luxemburg National Identification Number (Natural persons) -->
      <Entity id="aaf661ed-29ec-426d-8bf9-880cad298ebb" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Match idRef="Keywords_luxemburg_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_luxemburg_eu_telephone_number" />
            <Match idRef="Keywords_luxemburg_eu_mobile_number" />
          </Any>
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

#### <a name="keywords_nation_eu_passport_number"></a>Keywords_nation_eu_passport_number

- passport number
- 라트비아어 여권 번호
- passport 아니요
- passnummer

## <a name="luxemburg-national-identification-number-non-natural-persons"></a>룩셈부르크 국내 식별 번호 (비 자연적인 사람)

### <a name="format"></a>형식일

11자리 숫자
  
### <a name="pattern"></a>패턴

11자리 숫자
  
- 2 자리 숫자
- 선택적 공백 
- 3 자리 숫자 
- 선택적 공백
- 3 자리 숫자 
- 선택적 공백
- 2 자리 숫자
- 검사 숫자 1 개
    
### <a name="checksum"></a>제외

예
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- 이 함수는 해당  `Func_luxemburg_eu_tax_file_number_non_natural` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_luxemburg_eu_tax_file_number` 찾았습니다. 
    
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- 이 함수는 해당  `Func_luxemburg_eu_tax_file_number_non_natural` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
```xml
      <!-- Luxemburg National Identification Number (Non-natural persons) -->
      <Entity id="84bffa3a-d805-4788-a613-b1e4df3804cf" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number_non_natural" />
          <Match idRef="Keywords_luxemburg_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number_non_natural" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_luxemburg_eu_telephone_number" />
            <Match idRef="Keywords_luxemburg_eu_mobile_number" />
          </Any>
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
- 생년월일에 해당 하는 YYMMDD 형식의 6 자리 숫자 
- 대시 (선택 사항) 
- 두 글자로 된 생년월일 코드 
- 대시 (선택 사항) 
- 임의의 3 자리 숫자 
- 1 자리 성별 코드

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
- 공백 (선택 사항)
- 3 자리 숫자
- 공백 (선택 사항)
- 3 자리 숫자
    
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

#### <a name="keywords_malta_eu_drivers_license_number"></a>Keywords_malta_eu_driver ' s_license_number

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

## <a name="malta-identity-card-number"></a>몰타 id 카드 번호
이 중요 한 정보 유형은 다음 에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거 버 넌 스
- 레코드 관리
- Microsoft cloud app security

### <a name="format"></a>형식일

7 자리 숫자와 문자 1 개
  
### <a name="pattern"></a>패턴

7 자리 숫자와 문자 1 개:
  
- 7 자리 숫자 
- "M, G, A, P, L, H, B, Z"의 한 문자 (대/소문자 구분 안 함)
    
### <a name="checksum"></a>제외

해당 사항 없음
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- 정규식이 해당  `Regex_malta_eu_national_id_card` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_malta_eu_national_id_card` 찾았습니다. 
    
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 65% 신뢰합니다.
- 정규식이 해당  `Regex_malta_eu_national_id_card` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
```xml
      <!-- Malta Identity Card Number -->
      <Entity id="854b36b3-a388-4ac8-a4ec-677c2b5e4356" patternsProximity="300" recommendedConfidence="75">
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

7 자리 숫자 
  
### <a name="checksum"></a>제외

아니요
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- 정규식이 해당  `Regex_malta_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From  `Keywords_eu_passport_number_common` 또는 found의 키워드 `Keywords_malta_eu_passport_number` 입니다. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_malta_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- 여권 #
- 여권 #
- passportid
- passports
- passportno
- passport 아니요
- passportnumber
- 여권 번호
- passportnumbers
- 여권 번호

#### <a name="keywords_malta_eu_passport_number"></a>Keywords_malta_eu_passport_number

- numru-passaport
- numri tal-passaport
- Nru-passaport

## <a name="malta-tax-identification-number"></a>몰타 세금 식별 번호

### <a name="format"></a>형식일

몰타어 nationals의 경우:
- 지정 된 패턴에서 일곱 자리 숫자와 한 문자
  
몰타어 이외의 nationals 및 몰타어 엔터티:
- 9 자리 숫자
  
### <a name="pattern"></a>패턴

몰타어 nationals: 7 자리 숫자와 1 개 문자
  
- 7 자리 숫자 
- 1 개 문자 (대/소문자 구분 안 함)
    
몰타어 이외의 nationals 및 몰타어 엔터티: 9 자리 숫자
  
- 9 자리 숫자 
    
### <a name="checksum"></a>제외

해당 사항 없음
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Regex로  `Regex_malta_eu_tax_file_number`  가져오거나 해당 `Regex_malta_eu_tax_file_number_non_maltese_national` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_malta_eu_tax_file_number` 찾았습니다. 
    
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 65% 신뢰합니다.
- Regex로  `Regex_malta_eu_tax_file_number` 가져오거나 해당 `Regex_malta_eu_tax_file_number_non_maltese_national` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
```xml
      <!-- Malta Tax ID Number -->
      <Entity id="ec830c63-65f4-45d0-9d8c-910dc8334b20" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_tax_file_number_non_maltese_national" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number_non_maltese_national" />
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

선택 공백이 포함 된 8 자리 숫자

### <a name="pattern"></a>패턴

8-9 자리 숫자:
- 3 자리 숫자 
- 공백 (선택 사항) 
- 3 자리 숫자 
- 공백 (선택 사항) 
- 2-3 자리 숫자

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_netherlands_bsn 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keyword_netherlands_bsn에서 키워드가 발견 되었습니다.
- 체크섬이 통과됩니다.

```xml
      <!-- Netherlands Citizen's Service (BSN) Number -->
      <Entity id="c5f54253-ef7e-44f6-a578-440ed67e946d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_bsn" />
          <Match idRef="Keywords_netherlands_eu_national_id_card" />
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

## <a name="netherlands-drivers-license-number"></a>네덜란드 운전 면허 번호
이 중요 한 정보 유형 엔터티는 EU 드라이버의 라이선스 번호 중요 정보 유형 에서만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백과 구분 기호가 없는 10 자리 숫자
  
### <a name="pattern"></a>패턴

10 자리 숫자
  
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

#### <a name="keywords_netherlands_eu_drivers_license_number"></a>Keywords_netherlands_eu_driver ' s_license_number

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


## <a name="netherlands-passport-number"></a>네덜란드 여권 번호
이 중요 한 정보 유형 엔터티는 EU (유럽 여권 번호) 중요 한 정보 유형 으로만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백이 나 구분 기호가 없는 9 개의 문자 또는 숫자
  
### <a name="pattern"></a>패턴

9 개의 문자 또는 숫자
  
### <a name="checksum"></a>제외

해당 없음
  
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

#### <a name="keywords_netherlands_eu_passport_number"></a>Keywords_netherlands_eu_passport_number

- 네덜란드어 여권 번호
- passport number
- 네덜란드 여권 번호
- nederlanden, nummer ort
- 고 대/ort
- nederlanden paspoortnummer
- paspoortnummer

## <a name="netherlands-tax-identification-number"></a>네덜란드 세금 식별 번호
이 중요 한 정보 유형은 다음 에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거 버 넌 스
- 레코드 관리
- Microsoft cloud app security

### <a name="format"></a>형식일

공백이 나 구분 기호가 없는 9 자리 숫자
  
### <a name="pattern"></a>패턴

9 자리 숫자 
  
### <a name="checksum"></a>제외

예
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- 이 함수는 해당  `Func_netherlands_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_netherlands_eu_tax_file_number` 찾았습니다. 
    
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 65% 신뢰합니다.
- 이 함수는 해당  `Func_netherlands_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
```xml
      <!-- Netherlands Tax Identification Number -->
      <Entity id="01f42a64-eba7-4892-a67b-398237e4ade2" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
          <Match idRef="Keywords_netherlands_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
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


## <a name="netherlands-value-added-tax-number"></a>네덜란드 값 추가 된 세금 번호
이 중요 한 정보 유형은 다음 에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거 버 넌 스
- 레코드 관리
- Microsoft cloud app security

### <a name="format"></a>형식일

14 문자 영숫자 패턴

### <a name="pattern"></a>패턴

14 자리 영숫자 패턴:

- N 또는 n
- L 또는 l
- 선택적 공백, 점 또는 하이픈
- 9 자리 숫자
- 선택적 공백, 점 또는 하이픈
- B 또는 b
- 2 자리 숫자

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_netherlands_value_added_tax_number 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keywords_netherlands_value_added_tax_number에서 키워드가 발견 되었습니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Func_netherlands_value_added_tax_number 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.

```xml
      <!-- Netherlands Value Added Tax Number -->
      <Entity id="4f320d9b-4972-41ae-b337-88d499bb1ade" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_value_added_tax_number" />
          <Match idRef="Keywords_netherlands_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_value_added_tax_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_netherlands_value_added_tax_number"></a>Keyword_netherlands_value_added_tax_number

- vat 번호
- vat 아니요
- vat #
- wearde tafoege 세금 getal
- btw nûmer
- btw-nummer


## <a name="new-zealand-bank-account-number"></a>뉴질랜드 계좌 번호
이 중요 한 정보 유형은 다음 에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거 버 넌 스
- 레코드 관리
- Microsoft cloud app security

### <a name="format"></a>형식일

선택적 구분 기호가 있는 14-16 자리 패턴

### <a name="pattern"></a>패턴

선택적 구분 기호가 있는 14 ~ 16 자리 패턴:

- 2 자리 숫자
- 선택적 하이픈 또는 공백
- 3 ~ 4 자리 숫자
- 선택적 하이픈 또는 공백
- 7 자리 숫자
- 선택적 하이픈 또는 공백
- 2 ~ 3 자리 숫자
- 옵션 하이픈 또는 공백

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_new_zealand_bank_account_number 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keywords_new_zealand_bank_account_number에서 키워드가 발견 되었습니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Func_new_zealand_bank_account_number 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.

```xml
      <!-- New Zealand Bank Account Number -->
      <Entity id="1a97fc2b-dd2f-48f1-bc4e-2ddf25813956" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_new_zealand_bank_account_number" />
          <Match idRef="Keywords_new_zealand_bank_account_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_new_zealand_bank_account_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_new_zealand_bank_account_number"></a>Keyword_new_zealand_bank_account_number

- 계정 번호
- 은행 계좌
- bank_acct_id
- bank_acct_branch
- bank_acct_nbr


## <a name="new-zealand-drivers-license-number"></a>새 뉴질랜드 운전 면허 번호
이 중요 한 정보 유형은 다음 에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거 버 넌 스
- 레코드 관리
- Microsoft cloud app security

### <a name="format"></a>형식일

8 자리 영숫자 패턴

### <a name="pattern"></a>패턴

8 자리 영숫자 패턴

- 2 개 문자 
- 6 자리 숫자

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_newzealand_driver_license_number 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keywords_newzealand_driver_license_number에서 키워드가 발견 되었습니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 65% 신뢰합니다.
- Func_newzealand_driver_license_number 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.

```xml
      <!-- New Zealand Driver License Number -->
      <Entity id="1924b377-d287-49c9-a737-cfe7a8a2615a" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_newzealand_driver_license_number" />
          <Match idRef="Keywords_newzealand_driver_license_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_newzealand_driver_license_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_new_zealand_drivers_license_number"></a>Keyword_new_zealand_drivers_license_number

- driverlicence
- driverlicences
- 드라이버 lic
- 드라이버 라이선스
- 드라이버 라이선스
- driverslic
- 드라이버 라이선스
- driverslicences
- drivers lic
- 드라이버 driver'lics
- 드라이버 라이선스
- 라이선스 드라이버
- driver' lic
- driver'lics
- driver' 라이선스
- driver'licences
- 드라이버 ' lic
- 드라이버의 driver'lics
- 운전의 라이선스
- 드라이버 ' 라이선스
- driver'slic
- drivers (slics)
- driver'slicence
- driver'slicences
- 드라이버의 lic
- 운전 driver'lics
- 운전의 라이선스
- 운전 라이선스
- driverlic #
- driverlics #
- driverlicence #
- driverlicences #
- 드라이버 lic #
- 드라이버 driver'lics #
- 드라이버 라이선스 #
- 드라이버 라이선스 #
- driverslic #
- driverslics #
- 드라이버 라이선스 #
- driverslicences #
- drivers lic #
- 드라이버 driver'lics #
- 드라이버 라이선스 #
- 라이선스 드라이버 #
- driver' lic #
- driver'lics #
- driver' 라이선스 #
- driver'licences #
- 드라이버 ' lic #
- 드라이버의 driver'lics #
- 운전의 라이선스 #
- 드라이버 ' 라이선스 #
- driver'slic #
- drivers (slics) #
- driver'slicence #
- driver'slicences #
- 드라이버의 lic #
- 운전 driver'lics #
- 운전의 라이선스 #
- 운전 라이선스 #
- 
international driving permit
- international driving permits
- nz 자동차 연결
- 새 뉴질랜드 자동차 연결


## <a name="new-zealand-inland-revenue-number"></a>뉴질랜드 inland 수입 번호
이 중요 한 정보 유형은 다음 에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거 버 넌 스
- 레코드 관리
- Microsoft cloud app security

### <a name="format"></a>형식일

선택적 구분 기호가 있는 8 개 또는 9 자리 숫자

### <a name="pattern"></a>패턴

선택적 구분 기호가 있는 8 개 또는 9 자리 숫자

- 2 ~ 3 자리 숫자
- 선택적 공백 또는 하이픈
- 3 자리 숫자
- 선택적 공백 또는 하이픈
- 3 자리 숫자

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_new_zealand_inland_revenue_number 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keywords_new_zealand_inland_revenue_number에서 키워드가 발견 되었습니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Func_new_zealand_inland_revenue_number 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.

```xml
      <!-- New Zealand Inland Revenue Number -->
      <Entity id="dd0fe2bc-7bcf-455f-bac1-83b1e3eb25fd" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_new_zealand_inland_revenue_number" />
          <Match idRef="Keywords_new_zealand_inland_revenue_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_new_zealand_inland_revenue_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_new_zealand_inland_revenue_number"></a>Keyword_new_zealand_inland_revenue_number

- ird 아니요
- ird 아니요 #
- nz ird
- 뉴질랜드 ird
- ird 번호
- inland 수익 번호


## <a name="new-zealand-ministry-of-health-number"></a>뉴질랜드 보건부 (생명 번호)

### <a name="format"></a>형식일

3 개의 문자, 공백 (선택 사항) 및 4 자리 숫자

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

### <a name="keywords"></a>키워드

#### <a name="keyword_nz_terms"></a>Keyword_nz_terms

- NHI 
- New Zealand 
- 상태 
- 처리가 


## <a name="new-zealand-social-wlefare-number"></a>뉴질랜드 공유 wlefare 번호
이 중요 한 정보 유형은 다음 에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거 버 넌 스
- 레코드 관리
- Microsoft cloud app security

### <a name="format"></a>형식일

9 자리 숫자

### <a name="pattern"></a>패턴

9 자리 숫자

- 3 자리 숫자
- 선택적 하이픈
- 3 자리 숫자
- 선택적 하이픈
- 3 자리 숫자

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_newzealand_social_welfare_number 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keywords_newzealand_social_welfare_number에서 키워드가 발견 되었습니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 65% 신뢰합니다.
- Func_newzealand_social_welfare_number 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.

```xml
      <!-- Newzealand Social Welfare Number -->
      <Entity id="20f3c48d-4ac1-4cd2-86bd-34ecc1826e9d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_newzealand_social_welfare_number" />
          <Match idRef="Keywords_newzealand_social_welfare_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_newzealand_social_welfare_number" />
        </Pattern>
      </Entity>
    </Version>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_new_zealand_social_welfare_number"></a>Keyword_new_zealand_social_welfare_number

- 소셜 welfare #
- 소셜 welfare #
- 소셜 welfare No
- 소셜 welfare 번호
- swn #

   
## <a name="norway-identification-number"></a>노르웨이 식별 번호

### <a name="format"></a>형식일

11자리 숫자

### <a name="pattern"></a>패턴

11자리 숫자:
- 출생 날짜에 해당 하는 DDMMYY 형식의 6 자리 숫자 
- 3 자리 개별 번호 
- 두 개의 검사 숫자

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_norway_id_number 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keyword_norway_id_number에서 키워드가 발견 되었습니다.
- 체크섬이 통과됩니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
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
- 4 자리 숫자 
- 하이픈 
- 7 자리 숫자 
- 하이픈 
- 1 자리 숫자

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
  
- 5 자리 숫자 
- 슬래시
- 2 자리 숫자
- 슬래시
- 7 자리 숫자
    
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

#### <a name="keywords_poland_eu_drivers_license_number"></a>Keywords_poland_eu_driver ' s_license_number

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

3 개의 문자 및 6 자리 숫자

### <a name="pattern"></a>패턴

3 개의 문자 (대/소문자 구분 안 함)와 6 자리 숫자

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Func_polish_national_id 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_polish_national_id_passport_number의 키워드가 발견되었습니다.
- 체크섬이 통과됩니다.

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

#### <a name="keyword_poland_national_id_passport_number"></a>Keyword_poland_national_id_passport_number

- Dowód osobisty
- U r i dowodu osobistego
- Nazwa i u r i dowodu osobistego
- Nazwa i veiligheid dowodu osobistego
- Nazwa i nr dowodu tożsamości
- Dowód Tożsamości
- dow. 르.

   
## <a name="poland-national-id-pesel"></a>폴란드 국가 ID (PESEL)

### <a name="format"></a>형식일

11자리 숫자

### <a name="pattern"></a>패턴

- YYMMDD 형식의 출생 날짜를 나타내는 6 자리 숫자
- 4 자리 숫자
- 1 개 검사 숫자

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_pesel_identification_number 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_pesel_identification_number의 키워드가 발견되었습니다.
- 체크섬이 통과됩니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Func_pesel_identification_number 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- 체크섬이 통과됩니다.

```xml
      <!-- Poland National ID (PESEL) -->
      <Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_pesel_identification_number" />
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

2 개의 문자와 7 자리 숫자

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

#### <a name="keyword_poland_national_id_passport_number"></a>Keyword_poland_national_id_passport_number

- U r i (zportu)
- Veiligheid. 고 zportu
- 고 zport

## <a name="poland-regon-number"></a>폴란드 REGON 번호
이 중요 한 정보 유형은 다음 에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거 버 넌 스
- 레코드 관리
- Microsoft cloud app security

### <a name="format"></a>형식일

9 자리 또는 14 자리 숫자

### <a name="pattern"></a>패턴

9 자리 숫자 또는 14 자리 번호:

- 9 자리 숫자 또는 
- 9 자리 숫자
- 슬래시나
- 5 자리 숫자

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_polish_regon_number 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keywords_polish_regon_number에서 키워드가 발견 되었습니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 65% 신뢰합니다.
- Func_polish_regon_number 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.

```xml
      <!-- Polish REGON Number  -->
      <Entity id="fc87b421-f437-4f8b-b739-29a735ead0d9" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_regon_number" />
          <Match idRef="Keywords_polish_regon_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_polish_regon_number" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>키워드

#### <a name="keywords_poland_regon_number"></a>Keywords_poland_regon_number

- id가 regon입니다.
- 통계 번호
- 통계 id
- 통계적 없음
- regon 번호
- regonid #
- regonno #
- 회사 id
- companyid #
- companyidno #
- u r i statystyczny
- numeru regon
- numerstatystyczny #
- numeruregon #


## <a name="poland-tax-identification-number"></a>폴란드 세금 식별 번호
이 중요 한 정보 유형은 다음 에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거 버 넌 스
- 레코드 관리
- Microsoft cloud app security

### <a name="format"></a>형식일

공백이 나 구분 기호가 없는 11 자리 숫자
  
### <a name="pattern"></a>패턴

11자리 숫자
  
### <a name="checksum"></a>제외

예
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- 이 함수는 해당  `Func_poland_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_poland_eu_tax_file_number` 찾았습니다. 
    
  
```xml
      <!-- Poland Tax Identification Number -->
      <Entity id="1ff28b4d-40f2-49e9-b677-9606a88e2bca" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
          <Match idRef="Keywords_poland_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_poland_eu_tax_file_number"></a>Keywords_poland_eu_tax_file_number

- nip #
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

### <a name="format"></a>형식일

8 자리 숫자

### <a name="pattern"></a>패턴

8 자리 숫자

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
- 6 자리 숫자
- 공백
- 1 자리 숫자
    
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

#### <a name="keywords_portugal_eu_drivers_license_number"></a>Keywords_portugal_eu_driver ' s_license_number

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
  
- 1 개 문자 (대/소문자 구분 안 함)
- 6 자리 숫자
    
### <a name="checksum"></a>제외

아니요
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- 정규식이 해당  `Regex_portugal_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From  `Keywords_eu_passport_number_common` 또는 found의 키워드 `Keywords_portugal_eu_passport_number` 입니다. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_portugal_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- 여권 #
- 여권 #
- passportid
- passports
- passportno
- passport 아니요
- passportnumber
- 여권 번호
- passportnumbers
- 여권 번호

#### <a name="keywords_portugal_eu_passport_number"></a>Keywords_portugal_eu_passport_number

- número do passaporte
- 포르투갈어 (여권)
- 포르투갈어 # seport
- 포르투갈 passaporte
- passaporte n º
- 포트 n º
- números de passaporte
- 포르투갈 passports
- número passaporte
- números passaporte

## <a name="portugal-tax-identification-number"></a>포르투갈 세금 식별 번호

### <a name="format"></a>형식일

선택 공백이 있는 9 자리 숫자
  
### <a name="pattern"></a>패턴

- 3 자리 숫자
- 선택적 공백
- 3 자리 숫자
- 선택적 공백
- 3 자리 숫자
  
### <a name="checksum"></a>제외

예
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- 이 함수는 해당  `Func_portugal_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_portugal_eu_tax_file_number` 찾았습니다. 
    
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 65% 신뢰합니다.
- 이 함수는 해당  `Func_portugal_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
```xml
      <!-- Portugal Tax Identification Number -->
      <Entity id="65372402-3131-4f1e-9983-4439841d1f15" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
          <Match idRef="Keywords_portugal_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
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
- 8 자리 숫자
    
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

#### <a name="keywords_romania_eu_drivers_license_number"></a>Keywords_romania_eu_driver ' s_license_number

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

## <a name="romania-personal-numeric-code-cnp"></a>루마니아 p (personal numeric code)
이 중요 한 정보 유형은 다음 에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거 버 넌 스
- 레코드 관리
- Microsoft cloud app security

### <a name="format"></a>형식일

공백과 구분 기호가 없는 13 자리 숫자
  
### <a name="pattern"></a>패턴

- 1 자리 1-9
- 출생 날짜를 나타내는 6 자리 숫자 (YYMMDD)
- 2 자리 숫자 (01-52 또는 99 일 수 있음)
- 4 자리 숫자

### <a name="checksum"></a>제외

예
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- 이 함수는 해당  `Func_romania_eu_national_id_card` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_romania_eu_national_id_card` 찾았습니다. 
    
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- 이 함수는 해당  `Func_romania_eu_national_id_card` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
```xml
      <!-- Romania Personal Numerical Code (CNP) -->
      <Entity id="eb5fa399-fe28-4c67-8188-d63a616ed89c" patternsProximity="300" recommendedConfidence="85">
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
- From  `Keywords_eu_passport_number_common` 또는 found의 키워드 `Keywords_romania_eu_passport_number` 입니다. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_romania_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- 여권 #
- 여권 #
- passportid
- passports
- passportno
- passport 아니요
- passportnumber
- 여권 번호
- passportnumbers
- 여권 번호

#### <a name="keywords_romania_eu_passport_number"></a>Keywords_romania_eu_passport_number

numărul pașaportului numarul pasaportului numerele pașaportului Pașaport veiligheid

## <a name="russia-passport-number-domestic"></a>러시아 (국내) 여권 번호
이 중요 한 정보 유형은 다음 에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거 버 넌 스
- 레코드 관리
- Microsoft cloud app security

### <a name="format"></a>형식일

10 자리 숫자

### <a name="pattern"></a>패턴

10 자리 숫자:

- 2 자리 숫자
- 선택적 공백 또는 하이픈
- 2 자리 숫자
- 선택적 공백
- 6 자리 숫자

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Regex Regex_Russian_Passport_Number_Domestic는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keyword_Russian_Passport_Number에서 키워드가 발견 되었습니다.

```xml
      <!-- Russian Passport Number Domestic -->
      <Entity id="76ec2f5d-cedb-48e1-8070-1998794af445" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Russian_Passport_Number_Domestic" />
          <Match idRef="Keyword_Russian_Passport_Number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_russia_passport_number_domestic"></a>Keyword_russia_passport_number_domestic

- 여권 번호
- passport 아니요
- 여권 #
- 여권 번호
- passportno #
- passportnumber #
- паспорт нет
- паспорт id
- pоссийской паспорт
- pусский номер паспорта
- паспорт #
- паспортid #
- номер паспорта
- номерпаспорта #


## <a name="russia-passport-number-international"></a>러시아 (국제) 여권 번호
이 중요 한 정보 유형은 다음 에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거 버 넌 스
- 레코드 관리
- Microsoft cloud app security

### <a name="format"></a>형식일

9 자리 숫자

### <a name="pattern"></a>패턴

9 자리 숫자:

- 2 자리 숫자
- 선택적 공백 또는 하이픈
- 7 자리 숫자

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Regex Regex_Russian_Passport_Number_International는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keyword_Russian_Passport_Number에서 키워드가 발견 되었습니다.

```xml
      <!-- Russian Passport Number International -->
      <Entity id="ac5f4878-75e4-4b82-af2d-02e13ea9f411" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Russian_Passport_Number_International" />
          <Match idRef="Keyword_Russian_Passport_Number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_russia_passport_number_international"></a>Keywords_russia_passport_number_international

- 여권 번호
- passport 아니요
- 여권 #
- 여권 번호
- passportno #
- passportnumber #
- паспорт нет
- паспорт id
- pоссийской паспорт
- pусский номер паспорта
- паспорт #
- паспортid #
- номер паспорта
- номерпаспорта #


## <a name="saudi-arabia-national-id"></a>사우디 아라비아 국가 ID

### <a name="format"></a>형식일

10 자리 숫자

### <a name="pattern"></a>패턴

10 자리 연속 숫자

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

9 개의 문자 및 숫자

### <a name="pattern"></a>패턴

- 9 개의 문자 및 숫자:
- 문자 "F", "G", "S" 또는 "T" (대/소문자 구분 안 함) 
- 7 자리 숫자 
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
- 7 자리 숫자 
    
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

#### <a name="keywords_slovakia_eu_drivers_license_number"></a>Keywords_slovakia_eu_driver ' s_license_number

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
- vodičský preukaz

## <a name="slovakia-personal-number"></a>슬로바키아 개인 번호
이 중요 한 정보 유형은 다음 에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거 버 넌 스
- 레코드 관리
- Microsoft cloud app security

### <a name="format"></a>형식일

선택적 백슬래시를 포함 하는 9 자리 숫자
  
### <a name="pattern"></a>패턴

- 출생 날짜를 나타내는 6 자리 숫자
- 선택적 슬래시 (/)
- 3 자리 숫자
- 1 개의 선택적 검사 숫자
  
### <a name="checksum"></a>제외

예
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- 이 함수는 해당  `Func_slovakia_eu_national_id_card` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_slovakia_eu_national_id_card` 찾았습니다. 
    
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 65% 신뢰합니다.
- 이 함수는 해당  `Func_slovakia_eu_national_id_card` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
```xml
      <!-- Slovakia Personal Number -->
      <Entity id="951c26b7-3b35-4f73-924b-15dd599cb9ab" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
          <Match idRef="Keywords_slovakia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
        </Pattern>
      </Entity>
    </Version>
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
- 주민 등록 번호
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
- From  `Keywords_eu_passport_number_common` 또는 found의 키워드 `Keywords_slovakia_eu_passport_number` 입니다. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_slovakia_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- 여권 #
- 여권 #
- passportid
- passports
- passportno
- passport 아니요
- passportnumber
- 여권 번호
- passportnumbers
- 여권 번호

#### <a name="keywords_slovakia_eu_passport_number"></a>Keywords_slovakia_eu_passport_number

- číslo (u)
- čísla pasov
- pas č
- 포트 n °
- n °에이 포트

## <a name="slovenia-drivers-license-number"></a>슬로베니아 운전 면허 번호
이 중요 한 정보 유형 엔터티는 EU 드라이버의 라이선스 번호 중요 정보 유형 에서만 사용할 수 있습니다.

### <a name="format"></a>형식일

공백과 구분 기호를 사용 하지 않고 9 자리 숫자
  
### <a name="pattern"></a>패턴

9 자리 숫자
  
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

#### <a name="keywords_slovenia_eu_drivers_license_number"></a>Keywords_slovenia_eu_driver ' s_license_number

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

## <a name="slovenia-unique-master-citizen-number"></a>슬로베니아 고유 마스터 시민 번호
이 중요 한 정보 유형은 다음 에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거 버 넌 스
- 레코드 관리
- Microsoft cloud app security

### <a name="format"></a>형식일

공백이 나 구분 기호가 없는 13 자리 숫자
  
### <a name="pattern"></a>패턴

지정 된 패턴의 13 자리 숫자:
  
- 생년월일 (DDMMLLL)에 해당 하는 7 자리 숫자 이며 "LLL"은 출생 연도의 마지막 세 자리에 해당 합니다. 
- 출생 "50" 영역에 해당 하는 2 자리 숫자
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
      <!-- Slovenia Unique Master Citizen Number -->
      <Entity id="68948b27-803d-41e4-adf1-13e05eb541bb" patternsProximity="300" recommendedConfidence="85">
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
- 7 자리 숫자
    
### <a name="checksum"></a>제외

아니요
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- 정규식이 해당  `Regex_slovenia_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From  `Keywords_eu_passport_number_common` 또는 found의 키워드 `Keywords_slovenia_eu_passport_number` 입니다. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_slovenia_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- 여권 #
- 여권 #
- passportid
- passports
- passportno
- passport 아니요
- passportnumber
- 여권 번호
- passportnumbers
- 여권 번호

#### <a name="keywords_slovenia_eu_passport_number"></a>Keywords_slovenia_eu_passport_number

- številka potnega lista
- potek veljavnosti
- potni 목록 #
- datum rojstva
- potni 목록
- številke potnih listov

## <a name="slovenia-tax-identification-number"></a>슬로베니아 세금 식별 번호
이 중요 한 정보 유형은 다음 에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거 버 넌 스
- 레코드 관리
- Microsoft cloud app security

### <a name="format"></a>형식일

공백이 나 구분 기호가 없는 8 자리 숫자
  
### <a name="pattern"></a>패턴

- 1-9의 1 자리 숫자
- 6 자리 숫자
- 검사 숫자 1 개
  
### <a name="checksum"></a>제외

예
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- 이 함수는 해당  `Func_slovenia_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_slovenia_eu_tax_file_number` 찾았습니다. 
    
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 65% 신뢰합니다.
- 이 함수는 해당  `Func_slovenia_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
```xml
      <!-- Slovenia Tax Identification Number -->
      <Entity id="e47b071e-c352-4d70-8241-8c215ad65505" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovenia_eu_tax_file_number" />
          <Match idRef="Keywords_slovenia_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
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
- 생년월일에 해당 하는 YYMMDD 형식의 6 자리 숫자 
- 4 자리 숫자 
- 1 자리 참여 지표 
- 숫자 "8" 또는 "9" 
- 체크섬 숫자에 해당 하는 1 자리 숫자

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
- 생년월일에 해당 하는 YYMMDD 형식의 6 자리 숫자 
- 하이픈 
- 세기 및 성별에 따라 결정 되는 1 자리 숫자 
- 4 자리 출생 지역 코드 
- 이전 번호가 동일한 사람을 구분 하는 데 사용 되는 1 자리 숫자 
- 검사 숫자입니다.

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
  
- 8 자리 숫자 
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

#### <a name="keywords_spain_eu_drivers_license_number"></a>Keywords_spain_eu_driver ' s_license_number

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

## <a name="spain-dni"></a>스페인 DNI
이 중요 한 정보 유형은 다음 에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거 버 넌 스
- 레코드 관리
- Microsoft cloud app security

### <a name="format"></a>형식일

8 자리 숫자와 문자 1 개
  
### <a name="pattern"></a>패턴

7 자리 숫자와 문자 1 개
  
- 8 자리 숫자
- 선택적 공백 또는 하이픈
- 1 개의 확인 문자 (대/소문자 구분 안 함)
    
### <a name="checksum"></a>제외

예
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- 해당  `Func_spain_eu_DL_and_NI_number_citizen` `Func_spain_eu_DL_and_NI_number_foreigner` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_spain_eu_national_id_card"` 찾았습니다. 

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- 해당  `Func_spain_eu_DL_and_NI_number_citizen` `Func_spain_eu_DL_and_NI_number_foreigner` 패턴과 일치 하는 콘텐츠를 찾습니다. 

    
```xml
      <!-- Spain DNI -->
      <Entity id="8e6251b9-47b4-40e8-a42b-0f80876be192" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
        </Pattern>
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_foreigner" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_foreigner" />
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
  
- 두 자리 숫자 또는 문자 
- 1 자리 숫자 또는 문자 (선택 사항)
- 6 자리 숫자
    
### <a name="checksum"></a>제외

해당 사항 없음
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- 정규식이 해당  `Regex_spain_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From  `Keywords_eu_passport_number_common` 또는 found의 키워드 `Keywords_spain_eu_passport_number` 입니다. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_spain_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- 여권 #
- 여권 #
- passportid
- passports
- passportno
- passport 아니요
- passportnumber
- 여권 번호
- passportnumbers
- 여권 번호

#### <a name="keywords_spain_eu_passport_number"></a>Keywords_spain_eu_passport_number

- pasaporte
- número pasaporte
- españa pasaporte
- números de pasaporte
- número de pasaporte
- números pasaporte
- pasaporte 아니요
- 포트 n °
- n °에이 포트
- pasaporte 아니요
- pasaporte n °
- 스페인 여권


## <a name="spain-social-security-number-ssn"></a>스페인 SSN (사회 보장 번호)
이 중요 한 정보 유형 엔터티는 EU 주민 등록 번호 또는 동등한 ID 중요 정보 유형에 포함 되며 독립 실행형 중요 한 정보 유형 엔터티로 사용할 수 있습니다.

### <a name="format"></a>형식일

11-12자리 숫자

### <a name="pattern"></a>패턴

11-12 자리 숫자:
- 2 자리 숫자 
- 슬래시 (선택 사항) 
- 7 ~ 8 자리 숫자 
- 슬래시 (선택 사항) 
- 2 자리 숫자

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
이 중요 한 정보 유형은 다음 에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거 버 넌 스
- 레코드 관리
- Microsoft cloud app security

### <a name="format"></a>형식일

지정 된 패턴에 7 ~ 8 자리 숫자와 한 가지 또는 두 개의 문자가 있습니다.
  
### <a name="pattern"></a>패턴

스페인 국내 Id 카드가 있는 스페인어 (자연 사용자):
  
- 8 자리 숫자 
- 대문자 1 개 (대/소문자 구분) 
    
스페인 국가 Id 카드가 없는 상주 하지 않는 Spaniards
  
- 1 개의 대문자 "L" (대/소문자 구분)
- 7 자리 숫자
- 대문자 1 개 (대/소문자 구분) 
    
스페인 국가 Id 카드를 사용 하지 않고 14 년 동안 상주 하는 Spaniards:
  
- 1 개의 대문자 "K" (대/소문자 구분)
- 7 자리 숫자 
- 대문자 1 개 (대/소문자 구분)
    
Foreigner의 식별 번호를 사용 하는 Foreigners
  
- "X", "Y" 또는 "Z" (대/소문자 구분)의 대문자 1 개 
- 7 자리 숫자
- 대문자 1 개 (대/소문자 구분) 
    
Foreigner의 Id 번호가 없는 Foreigners
  
- "M"을 나타내는 대문자 1 개 (대/소문자 구분) 
- 7 자리 숫자
- 대문자 1 개 (대/소문자 구분) 
    
### <a name="checksum"></a>제외

예
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- 해당  `Func_spain_eu_tax_file_number` `Func_spain_eu_DL_and_NI_number_citizen` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_spain_eu_tax_file_number` 찾았습니다. 
    
DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- 해당  `Func_spain_eu_tax_file_number` `Func_spain_eu_DL_and_NI_number_citizen` 패턴과 일치 하는 콘텐츠를 찾습니다. 
    
```xml
      <!-- Spain Tax Identification Number -->
      <Entity id="10f0d113-b0e1-47dc-872a-a4f45b9376a3" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
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
  
- 6 자리 숫자 
- 하이픈
- 4 자리 숫자
    
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

### <a name="format"></a>형식일

10 또는 12 자리 숫자와 선택적 구분 기호

### <a name="pattern"></a>패턴

10 또는 12 자리 숫자와 선택적 구분 기호:
- 두 자리 숫자 (선택 사항) 
- YYMMDD 날짜 형식의 6자리 숫자 
- 구분 기호 "-" 또는 "+" (선택 사항)
- 4 자리 숫자

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- 이 함수는 해당 `Func_swedish_national_identifier` 패턴과 일치 하는 콘텐츠를 찾습니다.
- From 키워드를 `Keywords_swedish_national_identifier` 찾음
- 체크섬이 통과됩니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- 이 함수는 해당 `Func_swedish_national_identifier` 패턴과 일치 하는 콘텐츠를 찾습니다.
- 체크섬이 통과됩니다.


```xml
    <!-- Sweden National ID -->
    <Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
        <Match idRef="Keywords_swedish_national_identifier" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_swedish_national_identifier" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_swedish_national_identifier"></a>Keywords_swedish_national_identifier

- id 없음
- id 번호
- i #
- id 아니요
- identification number

- identifikationsnumret #
- identifikationsnumret
- identitetshandling
- id 문서
- identity no
- id 번호
- id-nummer
- 개인 id
- personnummer #
- personnummer
- skatteidentifikationsnummer
   
## <a name="sweden-passport-number"></a>스웨덴 여권 번호
이 중요 한 정보 유형 엔터티는 EU Passport 번호 중요 한 정보 형식에 포함 되며 독립 실행형 중요 한 정보 유형 엔터티로 사용할 수 있습니다.

### <a name="format"></a>형식일

8 자리 숫자

### <a name="pattern"></a>패턴

8 자리 연속 숫자

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- 정규식 Regex_sweden_passport_number 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- 다음 중 하나가 충족 됩니다.
    - Keyword_passport에서 키워드가 발견 되었습니다.
    - Keyword_sweden_passport에서 키워드가 발견 되었습니다.

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
  
- 출생 날짜에 해당 하는 8 자리 숫자 (YYYYMMDD) 
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
이 중요 한 정보 유형은 다음 에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거 버 넌 스
- 레코드 관리
- Microsoft cloud app security

### <a name="format"></a>형식일

지정 된 패턴의 10 자리 숫자와 기호
  
### <a name="pattern"></a>패턴

10 자리 숫자와 기호:
  
- 생년월일에 해당 하는 6 자리 숫자 (YYMMDD) 
- 더하기 기호 또는 빼기 기호
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
      <!-- Sweden Tax Identification Number -->
      <Entity id="139acba0-a5bc-4fbb-876d-f7a493ae8a40" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
          <Match idRef="Keywords_sweden_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_sweden_eu_telephone_number" />
            <Match idRef="Keywords_sweden_eu_mobile_number" />
          </Any>
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

4 개 문자 다음에 5-31 자 또는 숫자

### <a name="pattern"></a>패턴

4 개의 문자와 5-31 자의 문자 또는 숫자를 입력 합니다.
- 4 문자 은행 코드 (대/소문자 구분 안 함) 
- 선택적 공백 
- 4-28개 문자 또는 숫자[BBAN(기본 은행 계좌 번호)] 
- 선택적 공백 
- 1 ~ 3 개의 문자 또는 숫자 (BBAN의 나머지)

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


## <a name="switzerland-ssn-ahv-number"></a>스위스 SSN AHV 번호
이 중요 한 정보 유형은 다음 에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거 버 넌 스
- 레코드 관리
- Microsoft cloud app security

### <a name="format"></a>형식일

13 자리 숫자

### <a name="pattern"></a>패턴

13 자리 숫자:

- 3 자리 숫자-756
- 선택적 점
- 4 자리 숫자
- 선택적 점
- 4 자리 숫자
- 선택적 점
- 2 자리 숫자

### <a name="checksum"></a>제외

예

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.
- Func_swiss_social_security_number_ahv 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keywords_swiss_social_security_number_ahv에서 키워드가 발견 되었습니다.

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Func_swiss_social_security_number_ahv 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.

```xml
      <!-- Swiss SSN AHV Number -->
      <Entity id="277cfa4b-6eaa-4a1b-9492-099dec849971" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_swiss_social_security_number_ahv" />
          <Match idRef="Keywords_swiss_social_security_number_ahv" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_swiss_social_security_number_ahv" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_swiss_ssn_ahv_number"></a>Keyword_swiss_ssn_AHV_number

- ahv
- ssn
- 인
- 보험 번호
- personalidno #
- 주민 등록 번호
- 개인 id 번호
- 개인 식별 번호
- insuranceno #
- uniqueidno #
- 고유 id 번호
- avs 번호
- 개인 id 없음 versicherungsnummer
- identifikationsnummer
- einzigartige identität nicht
- sozialversicherungsnummer
- id personnelle id
- 
numéro de sécurité sociale

   
## <a name="taiwan-national-identification-number"></a>대만식 국가 식별 번호

### <a name="format"></a>형식일

1 개 문자 (영문)와 9 자리 숫자

### <a name="pattern"></a>패턴

1 개 문자 (영문)와 9 자리 숫자:
- 1 개 문자 (영문, 대/소문자 구분 안 함) 
- 숫자 "1" 또는 "2" 
- 8 자리 숫자

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

#### <a name="keyword_taiwan_national_id"></a>Keyword_taiwan_national_id

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
- 문자 "3" 
- 8 자리 숫자

비-생체 인식 여권 번호:
- 9 자리 숫자

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

10 개의 문자 및 숫자

### <a name="pattern"></a>패턴

10 개의 문자 및 숫자:
- 2 개 문자 (대/소문자 구분 안 함) 
- 8 자리 숫자

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
- 첫 번째 숫자는 0 또는 9가 아님 
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

#### <a name="keyword_thai_citizen_id"></a>Keyword_thai_citizen_Id

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

#### <a name="keyword_turkish_national_id"></a>Keyword_turkish_national_id

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
- 5 개 문자 (대/소문자 구분 안 함) 또는 문자 대신 숫자 "9"를 입력할 수 있습니다. 
- 1 자리 숫자 
- 날짜 형식의 5 자리 숫자 MMDDY 생년월일 (드라이버가 암 인 경우 50이 고 62 51은 01부터 12까지)로 증가 합니다.
- 2 개의 문자 (대/소문자 구분 안 함) 또는 문자 대신 숫자 "9" 
- 5 자리 숫자

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

2 개의 문자와 1-4 자리 숫자

### <a name="pattern"></a>패턴

2 개의 문자 (대/소문자 구분 안 함)와 1-4 번호

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
- 3 또는 10 자리 숫자 
- 공백 
- 3 자리 숫자 
- 공백 
- 4 자리 숫자

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

공백 또는 대시로 구분 된 7 개 문자 또는 9 개 문자

### <a name="pattern"></a>패턴

다음과 같은 두 가지 패턴을 사용할 수 있습니다.

- 두 문자 (유효한 NINOs이 접두사의 특정 문자만 사용 하며이 패턴의 유효성 검사는 대/소문자를 구분 하지 않음)
- 6 자리 숫자
- ' A ', ' B ', ' C ' 또는 ' d ' (접두사와 마찬가지로 접미사에서는 특정 문자만 허용 되며 대/소문자 구분 안 함)

또는

- 2 개 문자
- 공백 또는 대시
- 2 자리 숫자
- 공백 또는 대시
- 2 자리 숫자
- 공백 또는 대시
- 2 자리 숫자
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
- 주민 등록 번호
- insurance application

- medical application

- social insurance

- medical attention

- 소셜 보안
- great britain

- NI 번호
- NI (아니요)
- 니 #
- 니 #
- 소유권 #
- insurancenumber
- nationalinsurance #
- nationalinsurancenumber

    
## <a name="uk-unique-taxpayer-reference-number"></a>영국 고유 Taxpayer 참조 번호
이 중요 한 정보 유형은 다음 에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거 버 넌 스
- 레코드 관리
- Microsoft cloud app security

### <a name="format"></a>형식일

공백과 구분 기호가 없는 10 자리 숫자
 
  
### <a name="pattern"></a>패턴

10자리 숫자
  
### <a name="checksum"></a>제외

아니요
  
### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- 이 함수는 해당  `Func_uk_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다. 
- From 키워드를  `Keywords_uk_eu_tax_file_number` 찾았습니다. 
    
```xml
      <!-- U.K. Unique Taxpayer Reference Number -->
      <Entity id="ad4a8116-0db8-439a-b545-6d967642f0ec" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
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

주 (예: 뉴욕)에 따라 다음을 수행 합니다.
- ddd ddd ddd와 같이 9 자리 숫자는 일치 합니다.
- ddddddddd와 같은 9 자리 숫자가 일치 하지 않습니다.

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

- 상태 약어 (예: "\ \") 
- 상태 이름 (예: "뉴욕")

## <a name="us-individual-taxpayer-identification-number-itin"></a>미국 ITIN (개별 taxpayer 식별 번호)

### <a name="format"></a>형식일

"9"로 시작 하 고, "7" 또는 "8"을 네 번째 숫자로 포함 하 고, 필요에 따라 공백이 나 대시로 서식이 지정 된 9 자리 숫자

### <a name="pattern"></a>패턴

서식이
- 숫자 "9" 
- 2 자리 숫자 
- 공백 또는 대시 
- "7" 또는 "8" 
- 숫자 
- 공백 또는 대시 
- 4 자리 숫자

서식
- 숫자 "9" 
- 2 자리 숫자 
- "7" 또는 "8" 
- 5 자리 숫자

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

서식이 지정 되거나 서식 없는 패턴으로 표시 될 수 있는 9 자리 숫자

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

- SSA 번호
- social security number
- 소셜 보안 #
- 소셜 보안 #
- 소셜 보안 아니요
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

9 자리 숫자

### <a name="pattern"></a>패턴

9 자리 연속 숫자

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

## <a name="ukraine-passport-domestic"></a>우크라이나 passport 국내
이 중요 한 정보 유형은 다음 에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거 버 넌 스
- 레코드 관리
- Microsoft cloud app security

### <a name="format"></a>형식일

9 자리 숫자

### <a name="pattern"></a>패턴

9 자리 숫자

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Regex Regex_Ukraine_Passport_Domestic는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keyword_Ukraine_Passport_Domestic에서 키워드가 발견 되었습니다.

```xml
      <!-- Ukraine Passport Domestic -->
      <Entity id="1817a540-221f-4459-9202-3bd78b81d803" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_Ukraine_Passport_Domestic"/>
          <Match idRef="Keyword_Ukraine_Passport_Domestic"/>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_ukraine_passport_domestic"></a>Keyword_ukraine_passport_domestic

- 우크라이나 여권
- 여권 번호
- passport 아니요
- паспорт України
- номер паспорта
- персональний


## <a name="ukraine-passport-international"></a>우크라이나 여권 국제 전화
이 중요 한 정보 유형은 다음 에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거 버 넌 스
- 레코드 관리
- Microsoft cloud app security

### <a name="format"></a>형식일

8 자 영숫자 패턴

### <a name="pattern"></a>패턴

8 자리 영숫자 패턴:
- 두 개의 문자 또는 숫자
- 6 자리 숫자

### <a name="checksum"></a>제외

아니요

### <a name="definition"></a>정의

DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.
- Regex Regex_Ukraine_Passport_International는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.
- Keyword_Ukraine_Passport_International에서 키워드가 발견 되었습니다.

```xml
      <!-- Ukraine Passport International -->
      <Entity id="cfbe032d-22e0-4f28-ab68-d66e9641f1e2" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Ukraine_Passport_International"/>
          <Match idRef="Keyword_Ukraine_Passport_International"/>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_ukraine_passport_international"></a>Keyword_ukraine_passport_international

- 우크라이나 여권
- 여권 번호
- passport 아니요
- паспорт України
- номер паспорта
