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
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: DLP 정책에 사용할 수 있는 200가지 중요한 정보 유형이 있습니다. 이 문서에서는 이러한 모든 중요한 정보 유형을 나열하고 DLP 정책이 각 유형을 검색할 때 검색하는 정보를 보여 제공합니다.
ms.openlocfilehash: 92b6d6720da67274e820a57fec8d2ade338574f2
ms.sourcegitcommit: dc26169e485c3a31e1af9a5f495be9db75c49760
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60754168"
---
# <a name="sensitive-information-type-entity-definitions"></a>중요한 정보 유형 엔터티 정의

이 문서에는 모든 중요한 정보 유형 엔터티 정의가 나열됩니다. 각 정의는 DLP 정책이 각 유형을 검색하기 위해 검색하는 것을 보여줍니다. 중요한 정보 유형에 대한 자세한 내용은 중요한 정보 [유형을 참조하세요.](sensitive-information-type-learn-about.md)

> [!NOTE]
> 정확도 번호를 사용하는 신뢰도 수준(높음/중간/낮음)(숫자 값 1 ~100) 매핑
> - 낮은 신뢰도: 65 이하
> - 보통 신뢰도: 75
> - 높은 신뢰도: 85

## <a name="aba-routing-number"></a>ABA 라우팅 번호

### <a name="format"></a>형식

서식이 지정되거나 서식 없는 패턴일 수 있는 9자리 숫자

### <a name="pattern"></a>패턴

- 00-12, 21-32, 61-72 또는 80 범위의 두 자리 숫자
- 2자리 숫자
- 선택적 하이픈
- 4자리 숫자
- 선택적 하이픈
- 숫자


### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

정책은 300자 이내의 접근성으로 이러한 유형의 중요한 정보를 검색할 수 있다는 신뢰도 중간 정도의 신뢰를 가합니다.
- Func_aba_routing 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_ABA_Routing의 키워드가 발견되었습니다.

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있다는 신뢰도는 낮습니다.
- Func_aba_routing 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.

```xml
    <!-- ABA Routing Number -->
    <Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_aba_routing" />
      </Pattern>
    </Entity>
```


### <a name="keywords"></a>키워드

#### <a name="keyword_aba_routing"></a>Keyword_aba_routing

- aba number
- aba #
- aba
- abarouting #
- abaroutingnumber
- americanbankassociationrouting #
- americanbankassociationroutingnumber
- bankrouting #
- bankroutingnumber
- 라우팅 #
- 라우팅 아니요
- 라우팅 번호
- routing transit number
- 라우팅 #
- RTN


## <a name="argentina-national-identity-dni-number"></a>아르헨티나 국가 ID(DNI) 번호

### <a name="format"></a>형식

8자리 숫자(또는 기간이 없는 경우)

### <a name="pattern"></a>패턴

8자리 숫자:
- 2자리 숫자
- 선택적 기간
- 3자리 숫자
- 선택적 기간
- 3자리 숫자

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 정규식 Regex_argentina_national_id 일치하는 콘텐츠를 검색합니다.
- 검색된 Keyword_argentina_national_id 발견됩니다.

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
- cedula
- cédula
- dni
- documento nacional de identidad
- documento número
- documento numero
- registro nacional de las personas
- rnp

## <a name="argentina-unique-tax-identification-key-cuitcuil"></a>아르헨티나 고유 세금 식별 키(CUIT/CUIL)

### <a name="format"></a>형식

대시가 있는 11자리 숫자

### <a name="pattern"></a>패턴

대시가 있는 11자리 숫자:
- 20, 23, 24, 27, 30, 33 또는 34의 두 자리 숫자
- 하이픈(-)
- 8자리 숫자
- 하이픈(-)
- 검사 숫자 1개

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이 `Func_Argentina_Unique_Tax_Key` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 시작 `Keyword_Argentina_Unique_Tax_Key` 키워드가 발견됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 이 `Func_Argentina_Unique_Tax_Key` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.

```xml
    <!-- Argentina Unique Tax Identification Key (CUIT/CUIL) -->
      <Entity id="98da3da1-9199-4571-b7c4-b6522980b507" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_Argentina_Unique_Tax_Key" />
          <Match idRef="Keyword_Argentina_Unique_Tax_Key" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_Argentina_Unique_Tax_Key" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_argentina_unique_tax_key"></a>Keyword_Argentina_Unique_Tax_Key

- Clave Unica de Identificacion Tributaria
- CUIT
- 고유한 랩 식별 코드 
- Clave Única de Identificación Tributaria
- 고유한 실무 식별 코드
- CUIL
- 고유 세금 식별 키
- 고유 랩 식별 키
- 랩 식별의 고유 키
- 고유 작업 식별 코드
- 고유 작업 ID 코드
- 고유한 작업 식별 키
- 작업 ID의 고유 키
- 세금 식별의 고유 코드
- 세금 식별의 고유 키
- 고유 근로 식별 코드
- 고유한 근로자 식별 규약
- 고유 근로 식별 키
- 근로 식별의 고유 키
- tax ID
- taxID #
- taxId
- 일자 수
- tax number
- tax no
- tax #
- tax #
- taxpayer ID
- taxpayer number
- taxpayer no
- taxpayer #
- taxpayer #
- tax identity
- tax identification
- Número de Identificación Fiscal
- número de contribuyente


## <a name="australia-bank-account-number"></a>호주 은행 계좌 번호

### <a name="format"></a>형식

은행 지점 번호가 있는 경우 또는 없는 6-10자리 숫자

### <a name="pattern"></a>패턴

계정 번호는 6자리에서 10자리까지입니다.

호주 은행 지점 번호:
- 3자리 숫자
- 하이픈
- 3자리 숫자

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 정규식 Regex_australia_bank_account_number 일치하는 콘텐츠를 검색합니다.
- Keyword_australia_bank_account_number의 키워드가 발견되었습니다.
- Regex_australia_bank_account_number_bsb 정규식이 해당 패턴과 일치하는 콘텐츠를 찾습니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 정규식 Regex_australia_bank_account_number 일치하는 콘텐츠를 검색합니다.

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

## <a name="australia-business-number"></a>오스트레일리아 비즈니스 번호
이 중요한 정보 유형은 다음에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거버넌스
- 레코드 관리
- Microsoft 클라우드 앱 보안


### <a name="format"></a>형식

선택적 디지타이터가 있는 11자리 숫자

### <a name="pattern"></a>패턴

선택적 디지타이터가 있는 11자리 숫자:

- 2자리 숫자
- 선택적 하이픈 또는 공백
- 3자리 숫자
- 선택적 하이픈 또는 공백
- 3자리 숫자
- 선택적 하이픈 또는 공백
- 3자리 숫자

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이 Func_australian_business_number 일치하는 콘텐츠를 검색합니다.
- 검색된 Keywords_australian_business_number 발견됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 이 Func_australian_business_number 일치하는 콘텐츠를 검색합니다.

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

- australia business no
- business number
- abn #
- businessid #
- 비즈니스 ID
- abn
- businessno #

## <a name="australia-company-number"></a>오스트레일리아 회사 번호
이 중요한 정보 유형은 다음에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거버넌스
- 레코드 관리
- Microsoft 클라우드 앱 보안

### <a name="format"></a>형식

9자리 숫자(디지타이터)입니다.

### <a name="pattern"></a>패턴

9자리 숫자(디지타이터)입니다.

- 3자리 숫자
- 공백
- 3자리 숫자
- 공백
- 3자리 숫자


### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이 Func_Australian_Company_Number 일치하는 콘텐츠를 검색합니다.
- 검색된 Keyword_Australian_Company_Number 발견됩니다.

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있다는 신뢰도는 낮습니다.
- 이 Func_Australian_Company_Number 일치하는 콘텐츠를 검색합니다.

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

- can
- australia company no
- australia company no #
- australia company number(오스트레일리아 회사 번호
- australian company no
- australian company no #
- australian company number(오스트레일리아 회사 번호)

## <a name="australia-drivers-license-number"></a>호주 운전 면허 번호

### <a name="format"></a>형식

9개의 문자 및 숫자

### <a name="pattern"></a>패턴

9개의 문자 및 숫자:

- 2자리 숫자 또는 문자(대소문자 구분 안 )
- 2자리 숫자
- 5자리 숫자 또는 문자(대소문자 구분 안 )

또는

- 선택적 문자 1-2개(대소문자 구분 안 )
- 4-9자리 숫자

또는

- 9자리 숫자 또는 문자(대소문자 구분 안 )

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
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
- DriversLicence
- DriversLicences
- Drivers Lic
- Drivers Lics
- Drivers Licence
- Drivers Licences
- Driver'Lic
- Driver'Lics
- Driver'Licence
- Driver'Licences
- Driver'Lic
- Driver' Lics
- Driver' Licence
- Driver'Licences
- Driver'sLic
- Driver'sLics
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
- DriversLicence #
- DriversLicences #
- Drivers Lic#
- Drivers Lics#
- Drivers Licence#
- Drivers Licences#
- Driver'Lic #
- Driver'Lics #
- Driver'Licence #
- Driver'Licences #
- Driver' Lic#
- Driver' Lics#
- Driver' Licence#
- Driver' Licences#
- Driver'sLic #
- Driver'sLics #
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
- DriversLicense
- DriversLicenses
- Drivers License
- Drivers Licenses
- Driver'License
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
- DriversLicense #
- DriversLicenses #
- Drivers License#
- Drivers Licenses#
- Driver'License #
- Driver'Licenses #
- Driver' License#
- Driver' Licenses#
- Driver'sLicense #
- Driver'sLicenses #
- Driver's License#
- Driver's Licenses#

## <a name="australia-medical-account-number"></a>오스트레일리아 의료 계좌 번호

### <a name="format"></a>형식

10-11자리 숫자

### <a name="pattern"></a>패턴

10-11자리 숫자:
- 첫 번째 숫자는 2-6 범위에 있습니다.
- 9번째 숫자는 검사 숫자입니다.
- 10번째 숫자는 문제 숫자입니다.
- 11번째 숫자(선택 사항)는 개인 번호입니다.

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
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


## <a name="australia-passport-number"></a>호주 여권 번호

### <a name="format"></a>형식

영문자 8자 또는 9자

### <a name="pattern"></a>패턴

- 한 문자(N, E, D, F, A, C, U, X) 다음에 7자리 숫자 또는
- 두 문자(PA, PB, PC, PD, PE, PF, PU, PW, PX, PZ) 다음에 7자리가 입니다.

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- `Regex_australia_passport_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 시작 `Keyword_australia_passport_number` 키워드가 발견됩니다.

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있다는 신뢰도는 낮습니다.
- `Regex_australia_passport_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.

```xml
    <!-- Australia Passport Number -->
    <Entity id="29869db6-602d-4853-ab93-3484f905df50" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_passport_number" />
        <Match idRef="Keyword_australia_passport_number" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_australia_passport_number" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_australia_passport_number"></a>Keyword_australia_passport_number

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers
- passport details
- immigration and citizenship
- commonwealth of australia
- department of immigration
- national identity card
- travel document
- issuing authority


## <a name="australia-tax-file-number"></a>오스트레일리아 세금 파일 번호

### <a name="format"></a>형식

8-9자리 숫자

### <a name="pattern"></a>패턴

일반적으로 다음과 같이 공백이 있는 8-9자리 숫자
- 3자리 숫자
- 선택적 공백
- 3자리 숫자
- 선택적 공백
- 마지막 숫자가 검사 숫자인 2-3자리 숫자

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
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

## <a name="austria-drivers-license-number"></a>오스트리아 운전 면허 번호

### <a name="format"></a>형식

공백 및 디지타이터가 없는 8자리 숫자

### <a name="pattern"></a>패턴

8자리 숫자

### <a name="checksum"></a>체크섬

아니요

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.

- `Regex_austria_eu_driver's_license_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_driver's_license_number` `Keywords_austria_eu_driver's_license_number` 찾거나 찾은 경우

```xml
      <!-- Austria Driver's License Number -->
      <Entity id="682f18ce-44eb-482b-8198-2bcb96a0761e" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_austria_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv 라이선스
- driv 라이선스
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl 번호


#### <a name="keywords_austria_eu_drivers_license_number"></a>Keywords_austria_eu_driver s_license_number

- fuhrerschein
- führerschein
- Führerscheine
- Führerscheinnummer
- Führerscheinnummern

## <a name="austria-identity-card"></a>오스트리아 ID 카드
이 중요한 정보 유형은 다음에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거버넌스
- 레코드 관리
- Microsoft 클라우드 앱 보안

### <a name="format"></a>형식

문자, 숫자 및 특수 문자의 24자 조합

### <a name="pattern"></a>패턴

24자:

-  22개 문자(대/소문자 구분 안 ), 숫자, 백슬래시, 슬래시 또는 더하기 기호

- 두 글자(대/소문자 구분 안 ), 숫자, 백슬래시, 슬래시, 더하기 기호 또는 등호

### <a name="checksum"></a>체크섬

해당 사항 없음

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.

- `Regex_austria_eu_national_id_card`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 시작  `Keywords_austria_eu_national_id_card` 키워드가 발견됩니다.

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

- ID 번호
- national id
- personalausweis republik österreich

## <a name="austria-passport-number"></a>오스트리아 여권 번호

### <a name="format"></a>형식

문자 1개, 선택적 공백 및 7자리 숫자

### <a name="pattern"></a>패턴

문자 1자, 숫자 7자 및 공백 1개 조합:

- 한 문자(대소문자 구분 안 )
- 하나의 공백(선택 사항)
- 7자리 숫자

### <a name="checksum"></a>체크섬

해당 없음

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- `Regex_austria_eu_passport_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_passport_number` `Keywords_austria_eu_passport_number` 찾거나 찾은 경우
- `Regex_eu_passport_date1`정규식이 DD.MM.YYYY 형식의 날짜를 찾거나 키워드를 `Keywords_eu_passport_date` 찾은 경우

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- `Regex_austria_eu_passport_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_passport_number` `Keywords_austria_eu_passport_number` 찾거나 찾은 경우

```xml
      <!-- Austria Passport Number -->
      <Entity id="1c96ae4e-303b-447d-86c7-77113ac266bf" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_austria_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_austria_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_austria_eu_passport_number"></a>Keywords_austria_eu_passport_number

- reisepassnummer
- reisepasse
- No-Reisepass
- Nr-Reisepass
- Reisepass-Nr
- Passnummer
- reisepässe

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 문제의 날짜
- 만료 날짜

## <a name="austria-social-security-number"></a>오스트리아 사회 보장 번호

### <a name="format"></a>형식

지정된 형식의 10자리 숫자

### <a name="pattern"></a>패턴

10자리 숫자:

- 일련 번호에 해당하는 3자리 숫자
- 검사 숫자 1개
- 생년월일(DDMMYY)에 해당하는 6자리 숫자

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이  `Func_austria_eu_ssn_or_equivalent` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 시작  `Keywords_austria_eu_ssn_or_equivalent` 키워드가 발견됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 이  `Func_austria_eu_ssn_or_equivalent` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.

```xml
      <!-- Austria Social Security Number -->
      <Entity id="6896a906-86c9-4d19-a2da-6e43ccd19b7b" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_austria_eu_ssn_or_equivalent" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_austria_eu_telephone_number" />
            <Match idRef="Keywords_austria_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_austria_eu_ssn_or_equivalent"></a>Keywords_austria_eu_ssn_or_equivalent

- austrian ssn
- ehic number
- ehic no
- insurance code
- insurancecode #
- insurance number
- insurance no
- krankenkassennummer
- krankenversicherung
- socialsecurityno
- socialsecurityno #
- social security no
- social security number
- social security code
- sozialversicherungsnummer
- sozialversicherungsnummer #
- soziale sicherheit kein
- sozialesicherheitkein #
- ssn #
- ssn
- versicherungscode
- versicherungsnummer
- zdravstveno zavarovanje

## <a name="austria-tax-identification-number"></a>오스트리아 세금 ID 번호

### <a name="format"></a>형식

선택적 하이픈 및 슬래시가 있는 9자리 숫자

### <a name="pattern"></a>패턴

선택적 하이픈 및 슬래시가 있는 9자리 숫자:

- 2자리 숫자
- 하이픈(선택 사항)
- 3자리 숫자
- 슬래시(선택 사항)
- 4자리 숫자

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이  `Func_austria_eu_tax_file_number` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 시작  `Keywords_austria_eu_tax_file_number` 키워드가 발견됩니다.

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있다는 신뢰도는 낮습니다.
- 이  `Func_austria_eu_tax_file_number` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.

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
- st.nr.
- steuernummer
- tax id
- tax identification no
- tax identification number
- tax no #
- tax no
- tax number
- tax registration number
- 에 대한 나타 #
- 일자 #
- 일자 수 #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #
- tax number

## <a name="austria-value-added-tax"></a>오스트리아 부가가치세
이 중요한 정보 유형은 다음에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거버넌스
- 레코드 관리
- Microsoft 클라우드 앱 보안

### <a name="format"></a>형식

11자 영문 패턴

### <a name="pattern"></a>패턴

11자 영문자 패턴:

- A 또는 a
- T 또는 t
- 선택적 공간
- U 또는 u
- 선택적 공간
- 2-3자리 숫자
- 선택적 공간
- 4자리 숫자
- 선택적 공간
- 1-2자리 숫자

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이 Func_Austria_Value_Added_Tax 일치하는 콘텐츠를 검색합니다.
- 검색된 Keyword_Austria_Value_Added_Tax 발견됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 이 Func_Austria_Value_Added_Tax 일치하는 콘텐츠를 검색합니다.

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

- vat number
- vat #
- austrian vat number
- vat no.
- vatno #
- 부가가치세 번호
- austrian vat
- mwst
- umsatzsteuernummer
- mwstnummer
- ust.-identifikationsnummer
- umsatzsteuer-identifikationsnummer
- vat identification number
- atu number
- uid number


## <a name="azure-documentdb-auth-key"></a>Azure DocumentDB auth 키

### <a name="format"></a>형식

문자열 "DocumentDb" 다음에 아래 패턴에 설명된 문자와 문자열입니다.

### <a name="pattern"></a>패턴

- 문자열 "DocumentDb"
- 3~200자 사이의 대문자, 숫자, 기호, 특수 문자 또는 공백 조합
- 기호(>), 등호(=), 인용 부호(") 또는 아포스트로피(')
- 대문자 86자, 숫자, 슬래시(/) 또는 더하기 기호(+)의 조합
- 등호 2개(=)

### <a name="checksum"></a>체크섬

아니요

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 정규식 CEP_Regex_AzureDocumentDBAuthKey 일치하는 콘텐츠를 검색합니다.
- 정규식 CEP_CommonExampleKeywords 일치하는 콘텐츠를 찾을 수 없습니다.

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

기술적으로 이 중요한 정보 유형은 키워드 목록이 아닌 정규식을 사용하여 이러한 키워드를 식별합니다.

- contoso
- fabrikam
- northwind
- 샌드박스
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a>Azure IAAS 데이터베이스 연결 문자열 및 Azure SQL 연결 문자열

### <a name="format"></a>형식

문자열 "Server", "server", "data source" 다음에 문자열 "cloudapp.azure"를 포함하여 아래 패턴에 설명된 문자와 문자열이 추가됩니다.<!--no-hyperlink-->com" 또는 "cloudapp.azure.<!--no-hyperlink-->net" 또는 "database.windows.<!--no-hyperlink-->net", 문자열 "Password" 또는 "password" 또는 "pwd".

### <a name="pattern"></a>패턴

- 문자열 "Server", "server" 또는 "data source"
- 공백 문자 0-2개
- 등호(=)
- 공백 문자 0-2개
- 1에서 200 사이의 대문자, 숫자, 기호, 특수 문자 또는 공백의 조합
- 문자열 "cloudapp.azure.<!--no-hyperlink-->com", "cloudapp.azure.<!--no-hyperlink-->net", "database.windows.<!--no-hyperlink-->net"
- 1에서 300 사이의 대문자, 숫자, 기호, 특수 문자 또는 공백 조합
- 문자열 "Password", "password" 또는 "pwd"
- 공백 문자 0-2개
- 등호(=)
- 공백 문자 0-2개
- 세미콜론(;), 인용 부호(") 또는 아포스트로피(')가 아닌 하나 이상의 문자
- 세미코론(;), 인용 부호(") 또는 아포스트로피(')

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 정규식 CEP_Regex_AzureConnectionString 일치하는 콘텐츠를 검색합니다.
- 정규식 CEP_CommonExampleKeywords 일치하는 콘텐츠를 찾을 수 없습니다.

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

기술적으로 이 중요한 정보 유형은 키워드 목록이 아닌 정규식을 사용하여 이러한 키워드를 식별합니다.

- contoso
- fabrikam
- northwind
- 샌드박스
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-iot-connection-string"></a>Azure IoT 연결 문자열

### <a name="format"></a>형식

문자열 "HostName" 다음에 아래 패턴에 설명된 문자와 문자열(문자열 "azure-devices")입니다.<!--no-hyperlink-->net" 및 "SharedAccessKey".

### <a name="pattern"></a>패턴

- 문자열 "HostName"
- 공백 문자 0-2개
- 등호(=)
- 공백 문자 0-2개
- 1에서 200 사이의 대문자, 숫자, 기호, 특수 문자 또는 공백의 조합
- 문자열 "azure-devices.<!--no-hyperlink-->net"
- 1에서 200 사이의 대문자, 숫자, 기호, 특수 문자 또는 공백의 조합
- 문자열 "SharedAccessKey"
- 공백 문자 0-2개
- 등호(=)
- 공백 문자 0-2개
- 대문자, 숫자, 슬래시(/) 또는 더하기 기호(+)의 조합
- 등호(=)

### <a name="checksum"></a>체크섬

아니요

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 정규식은 CEP_Regex_AzureIoTConnectionString 일치하는 콘텐츠를 검색합니다.
- 정규식 CEP_CommonExampleKeywords 일치하는 콘텐츠를 찾을 수 없습니다.

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

기술적으로 이 중요한 정보 유형은 키워드 목록이 아닌 정규식을 사용하여 이러한 키워드를 식별합니다.

- contoso
- fabrikam
- northwind
- 샌드박스
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-publish-setting-password"></a>Azure 게시 설정 암호

### <a name="format"></a>형식

문자열 "userpwd=" 다음에 영문 문자열이 오게 됩니다.

### <a name="pattern"></a>패턴

- 문자열 "userpwd="
- 소문자 60자 또는 숫자 조합
- 인용 부호(")

### <a name="checksum"></a>체크섬

아니요

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 정규식 CEP_Regex_AzurePublishSettingPasswords 일치하는 콘텐츠를 검색합니다.
- 정규식 CEP_CommonExampleKeywords 일치하는 콘텐츠를 찾을 수 없습니다.


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

기술적으로 이 중요한 정보 유형은 키워드 목록이 아닌 정규식을 사용하여 이러한 키워드를 식별합니다.

- contoso
- fabrikam
- northwind
- 샌드박스
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-redis-cache-connection-string"></a>Azure Redis 캐시 연결 문자열

### <a name="format"></a>형식

문자열 "redis.cache.windows.<!--no-hyperlink-->net" 다음에 문자열 "password" 또는 "pwd"를 포함하여 아래 패턴에 설명된 문자와 문자열이 표시됩니다.

### <a name="pattern"></a>패턴

- 문자열 "redis.cache.windows.<!--no-hyperlink-->net"
- 1에서 200 사이의 대문자, 숫자, 기호, 특수 문자 또는 공백의 조합
- 문자열 "password" 또는 "pwd"
- 공백 문자 0-2개
- 등호(=)
- 공백 문자 0-2개
- 대문자, 숫자, 슬래시(/) 또는 더하기 기호(+)가 있는 43자 조합
- 등호(=)

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 정규식 CEP_Regex_AzureRedisCacheConnectionString 일치하는 콘텐츠를 검색합니다.
- 정규식 CEP_CommonExampleKeywords 일치하는 콘텐츠를 찾을 수 없습니다.

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

기술적으로 이 중요한 정보 유형은 키워드 목록이 아닌 정규식을 사용하여 이러한 키워드를 식별합니다.

- contoso
- fabrikam
- northwind
- 샌드박스
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-sas"></a>Azure SAS

### <a name="format"></a>형식

문자열 "sig" 다음에 아래 패턴에 설명된 문자와 문자열입니다.

### <a name="pattern"></a>패턴

- 문자열 "sig"
- 공백 문자 0-2개
- 등호(=)
- 공백 문자 0-2개
- 대문자, 숫자 또는 백분율 기호(%) 중 소문자 또는 대문자인 43-53자 사이의 조합
- 문자열 "%3d"
- 대문자, 숫자 또는 백분율 기호(%)가 아닌 문자

### <a name="checksum"></a>체크섬

아니요

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 정규식 CEP_Regex_AzureSAS 일치하는 콘텐츠를 검색합니다.

```xml
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a>Azure 서비스 버스 연결 문자열

### <a name="format"></a>형식

문자열 "Servicebus.windows"를 포함하여 아래 패턴에 설명된 문자와 문자열이 이어지며 문자열 "EndPoint"가 그 다음에 오게 됩니다.<!--no-hyperlink-->net" 및 "SharedAccesKey".

### <a name="pattern"></a>패턴

- 문자열 "EndPoint"
- 공백 문자 0-2개
- 등호(=)
- 공백 문자 0-2개
- 1에서 200 사이의 대문자, 숫자, 기호, 특수 문자 또는 공백의 조합
- 문자열 "servicebus.windows.<!--no-hyperlink-->net"
- 1에서 200 사이의 대문자, 숫자, 기호, 특수 문자 또는 공백의 조합
- 문자열 "SharedAccessKey"
- 공백 문자 0-2개
- 등호(=)
- 공백 문자 0-2개
- 대문자, 숫자, 슬래시(/) 또는 더하기 기호(+)가 있는 43자 조합
- 등호(=)

### <a name="checksum"></a>체크섬

아니요

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 정규식 CEP_Regex_AzureServiceBusConnectionString 일치하는 콘텐츠를 검색합니다.
- 정규식 CEP_CommonExampleKeywords 일치하는 콘텐츠를 찾을 수 없습니다.

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

기술적으로 이 중요한 정보 유형은 키워드 목록이 아닌 정규식을 사용하여 이러한 키워드를 식별합니다.

- contoso
- fabrikam
- northwind
- 샌드박스
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-storage-account-key"></a>Azure 저장소 계정 키

### <a name="format"></a>형식

문자열 "DefaultEndpointsProtocol"에 문자열 "AccountKey"를 포함하여 아래 패턴에 설명된 문자와 문자열이 이어지며

### <a name="pattern"></a>패턴

- 문자열 "DefaultEndpointsProtocol"
- 공백 문자 0-2개
- 등호(=)
- 공백 문자 0-2개
- 1에서 200 사이의 대문자, 숫자, 기호, 특수 문자 또는 공백의 조합
- 문자열 "AccountKey"
- 공백 문자 0-2개
- 등호(=)
- 공백 문자 0-2개
- 대문자, 숫자, 슬래시(/) 또는 더하기 기호(+)가 있는 86자 조합
- 등호 2개(=)

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 정규식 CEP_Regex_AzureStorageAccountKey 일치하는 콘텐츠를 검색합니다.
- 정규식 CEP_AzureEmulatorStorageAccountFilter 일치하는 콘텐츠를 찾을 수 없습니다.
- 정규식 CEP_CommonExampleKeywords 일치하는 콘텐츠를 찾을 수 없습니다.

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

기술적으로 이 중요한 정보 유형은 키워드 목록이 아닌 정규식을 사용하여 이러한 키워드를 식별합니다.

- Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw==

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

기술적으로 이 중요한 정보 유형은 키워드 목록이 아닌 정규식을 사용하여 이러한 키워드를 식별합니다.

- contoso
- fabrikam
- northwind
- 샌드박스
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-storage-account-key-generic"></a>Azure Storage 계정 키(일반)

### <a name="format"></a>형식

아래 패턴에 설명된 86개 이하 또는 대문자, 자릿수, 슬래시(/) 또는 더하기 기호(+)의 조합입니다.

### <a name="pattern"></a>패턴

- 기호(>), 아포스트로피('), 등호(=), 따로 표시(") 또는 숫자 기호(#) 중 하나까지입니다.
- 대문자, 숫자, 슬래시(/) 또는 더하기 기호(+)가 있는 86자 조합
- 등호 2개(=)

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 정규식 CEP_Regex_AzureStorageAccountKeyGeneric 일치하는 콘텐츠를 검색합니다.

```xml
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```
## <a name="belgium-drivers-license-number"></a>벨기에 운전 면허 번호

### <a name="format"></a>형식

공백 및 디지타이터가 없는 10자리 숫자

### <a name="pattern"></a>패턴

10자리 숫자

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- `Regex_belgium_eu_driver's_license_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를 `Keywords_eu_driver's_license_number` `Keywords_belgium_eu_driver's_license_number` 찾거나 찾은 경우

```xml
      <!-- Belgium Driver's License Number -->
      <Entity id="d89fd329-9324-433c-b687-2c37bd5166f3" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_belgium_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드


#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv 라이선스
- driv 라이선스
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl 번호

#### <a name="keywords_belgium_eu_drivers_license_number"></a>Keywords_belgium_eu_driver s_license_number

- rijbewijs
- rijbewijsnummer
- führerschein
- führerscheinnummer
- füehrerscheinnummer
- fuhrerschein
- fuehrerschein
- fuhrerscheinnummer
- fuehrerscheinnummer
- permis de conduire
- numéro permis conduire


## <a name="belgium-national-number"></a>벨기에 국가 번호

### <a name="format"></a>형식

11자리 숫자와 선택적분자

### <a name="pattern"></a>패턴

11자리 숫자와 구분 기호:
- YY 형식의 6자리 숫자와 2개의 선택적 기간 생년월일용 MM.DD
- 점, 대시, 공백의 선택적 delimiter
- 3개의 일직선 숫자(남성의 경우 홀수, 여성의 경우 홀수)
- 점, 대시, 공백의 선택적 delimiter
- 검사 숫자 2개

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 이 Func_belgium_national_number 일치하는 콘텐츠를 검색합니다.
- 검색된 Keyword_belgium_national_number 발견됩니다.
- 체크섬이 통과됩니다.

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있다는 신뢰도는 낮습니다.
- 이 Func_belgium_national_number 일치하는 콘텐츠를 검색합니다.
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

- belasting aantal
- bnn #
- bnn
- carte d'identité
- IDENTIFIANT NATIONAL
- identifiantnational #
- identificatie
- identification
- identifikation
- identifikationsnummer
- identifizierung
- identité
- identiteit
- identiteitskaart
- ID
- inscription
- national number
- national register
- nationalnumber #
- nationalnumber
- nif #
- nif
- numéro d'assuré
- numéro de registre national
- numéro de sécurité
- numéro d'identification
- numéro d'immatriculation
- numéro national
- numéronational #
- 개인 ID 번호
- personalausweis
- personalidnumber #
- registratie
- registration
- registrationsnumme
- registrierung
- social security number
- ssn #
- ssn
- steuernummer
- tax id
- tax identification no
- tax identification number
- tax no #
- tax no
- tax number
- tax registration number
- 에 대한 나타 #
- 일자 #
- 일자 수 #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #

## <a name="belgium-passport-number"></a>벨기에 여권 번호

### <a name="format"></a>형식

2개의 문자와 공백이나 따로 6자리 숫자(공백 또는 따로 문자 없음)

### <a name="pattern"></a>패턴

2개의 문자와 6자리 숫자

### <a name="checksum"></a>체크섬

해당 없음

### <a name="definition"></a>정의

 DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- `Regex_belgium_eu_passport_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_passport_number` `Keywords_belgium_eu_passport_number` 찾거나 찾은 경우
- 정규식은 DD MM YY 형식의 날짜 또는 에서 키워드를 찾거나 `Regex_eu_passport_date2` `Keywords_eu_passport_date` 찾을 수 `Keywords_belgium_eu_passport_number` 있습니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- `Regex_belgium_eu_passport_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_passport_number` `Keywords_belgium_eu_passport_number` 찾거나 찾은 경우

```xml
      <!-- Belgium Passport Number -->
      <Entity id="d7b1315b-21ca-4774-a32a-596010ff78fd" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_belgium_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_belgium_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date2" />
            <Match idRef="Keywords_eu_passport_date" />
            <Match idRef="Keywords_belgium_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_belgium_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>

```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_belgium_eu_passport_number"></a>Keywords_belgium_eu_passport_number

- numéro passeport
- paspoort nr
- paspoort-nr
- paspoortnummer
- paspoortnummers
- Passeport carte
- Passeport livre
- Pass-Nr
- Passnummer
- kein 재구성

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 문제의 날짜
- 만료 날짜

## <a name="belgium-value-added-tax-number"></a>벨기에 부가가치 세금 번호
이 중요한 정보 유형은 다음에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거버넌스
- 레코드 관리
- Microsoft 클라우드 앱 보안

### <a name="format"></a>형식

12자 영문 패턴

### <a name="pattern"></a>패턴

12자 영문 패턴:

- 문자 B 또는 b
- E 또는 e 문자
- 숫자 0
- 1에서 9까지의 숫자
- 선택적 점 또는 하이픈 또는 공백
- 4자리 숫자
- 선택적 점 또는 하이픈 또는 공백
- 4자리 숫자


### <a name="checksum"></a>체크섬

예


### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이 Func_belgium_value_added_tax_number 패턴과 일치하는 콘텐츠를 검색합니다.
- 검색된 Keywords_belgium_value_added_tax_number 발견됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 이 Func_belgium_value_added_tax_number 패턴과 일치하는 콘텐츠를 검색합니다.

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

- nº tva
- vat number
- vat no
- numéro t.v.a
- umsatzsteuer-identifikationsnummer
- umsatzsteuernummer
- btw
- btw #
- vat #


## <a name="brazil-cpf-number"></a>브라질 CPF 번호

### <a name="format"></a>형식

서식이 있거나 서식이 없을 수 있는 검사 숫자를 포함하는 11자리 숫자

### <a name="pattern"></a>패턴

서식 있는 형식:
- 3자리 숫자
- 기간
- 3자리 숫자
- 기간
- 3자리 숫자
- 하이픈
- 검사 숫자인 2자리 숫자

비형성:
- 마지막 2자리 숫자가 검사 숫자인 11자리 숫자

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이 Func_brazil_cpf 일치하는 콘텐츠를 검색합니다.
- 검색된 Keyword_brazil_cpf 발견됩니다.
- 체크섬이 통과됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 이 Func_brazil_cpf 일치하는 콘텐츠를 검색합니다.
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
- Identification
- 등록
- 수익
- Cadastro de Pessoas Físicas
- Imposto
- Identificação
- Inscrição
- Receita


## <a name="brazil-legal-entity-number-cnpj"></a>브라질 법인 번호(CNPJ)

### <a name="format"></a>형식

등록 번호, 지점 번호, 검사 숫자 및 구분 기호를 포함하는 14자리 숫자

### <a name="pattern"></a>패턴

14자리 숫자와 구분 기호:

- 2자리 숫자
- 기간
- 3자리 숫자
- 기간
- 3자리 숫자(처음 8자리 숫자는 등록 번호)
- 슬래시
- 4자리 분기 번호
- 하이픈
- 검사 숫자인 2자리 숫자

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이 Func_brazil_cnpj 일치하는 콘텐츠를 검색합니다.
- 검색된 Keyword_brazil_cnpj 발견됩니다.
- 체크섬이 통과됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 이 Func_brazil_cnpj 일치하는 콘텐츠를 검색합니다.
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
- Empresa


## <a name="brazil-national-identification-card-rg"></a>브라질 국가 ID 카드(RG)

### <a name="format"></a>형식

Registro Geral(이전 형식): 9자리 숫자

Registro de Identidade(RIC)(새 형식): 11자리

### <a name="pattern"></a>패턴

Registro Geral(이전 형식):
- 2자리 숫자
- 기간
- 3자리 숫자
- 기간
- 3자리 숫자
- 하이픈
- 검사 숫자인 1자리 숫자

Registro de Identidade(RIC)(새 형식):
- 10자리 숫자
- 하이픈
- 검사 숫자인 1자리 숫자

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이 Func_brazil_rg 일치하는 콘텐츠를 검색합니다.
- 검색된 Keyword_brazil_rg 발견됩니다.
- 체크섬이 통과됩니다.


```xml
      <!-- Brazil National ID Card (RG) -->
      <Entity id="486de900-db70-41b3-a886-abdf25af119c" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_brazil_rg" />
          <Match idRef="Keyword_brazil_rg" />
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
- RG(이 키워드는 대소문자 구분)
- RIC(이 키워드는 대소문자 구분)


## <a name="bulgaria-drivers-license-number"></a>불가리아 운전 면허 번호

### <a name="format"></a>형식

공백 및 디지타이터가 없는 9자리 숫자

### <a name="pattern"></a>패턴

9자리 숫자

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- `Regex_bulgaria_eu_driver's_license_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_driver's_license_number` `Keywords_bulgaria_eu_driver's_license_number` 찾거나 찾은 경우

```xml
      <!-- Bulgaria Driver's License Number -->
      <Entity id="66d39258-94c2-43b2-804b-aa312258e54b" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv 라이선스
- driv 라이선스
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl 번호


#### <a name="keywords_bulgaria_eu_drivers_license_number"></a>Keywords_bulgaria_eu_driver s_license_number

- свидетелство за управление на мпс
- свидетелство за управление на моторно превозно средство
- сумпс
- шофьорска книжка
- шофьорски книжки

## <a name="bulgaria-uniform-civil-number"></a>불가리아 유니폼 내선 번호
이 중요한 정보 유형은 다음에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거버넌스
- 레코드 관리
- Microsoft 클라우드 앱 보안

### <a name="format"></a>형식

공백 및 디지타이터가 없는 10자리 숫자

### <a name="pattern"></a>패턴

공백 및 디지타이터가 없는 10자리 숫자

- 생년월일(YYMMDD)에 해당하는 6자리 숫자
- 생년월일 순서에 해당하는 2자리 숫자
- 성별에 해당하는 1자리 숫자: 남성의 10진수와 여성의 홀수 숫자
- 검사 숫자 1개

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이  `Func_bulgaria_eu_national_id_card` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 시작  `Keywords_bulgaria_eu_national_id_card` 키워드가 발견됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 이  `Func_bulgaria_eu_national_id_card` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.

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
- bucn #
- bucn
- edinen grazhdanski nomer
- egn #
- egn
- identification number
- national id
- national number
- nationalnumber #
- nationalnumber
- personal id
- personal no
- personal number
- personalidnumber #
- social security number
- ssn #
- ssn
- uniform 군데이트 ID
- uniform이 아니요
- uniform 내선 번호
- uniformcivilno #
- uniformcivilno
- uniformcivilnumber #
- uniformcivilnumber
- 고유 시민권 번호
- егн #
- егн
- единен граждански номер
- идентификационен номер
- личен номер
- лична идентификация
- лично не
- национален номер
- номер на гражданството
- униформ ID
- униформ граждански ID
- униформ граждански не
- униформ граждански номер
- униформгражданскиid #
- униформгражданскине. #


## <a name="bulgaria-passport-number"></a>불가리아 여권 번호

### <a name="format"></a>형식

공백 및 디지타이터가 없는 9자리 숫자

### <a name="pattern"></a>패턴

9자리 숫자

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- `Regex_bulgaria_eu_passport_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_passport_number` `Keywords_bulgaria_eu_passport_number` 찾거나 찾은 경우
- `Regex_eu_passport_date1`정규식이 DD.MM.YYYY 형식의 날짜를 찾거나 키워드를 `Keywords_eu_passport_date` 찾은 경우

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- `Regex_bulgaria_eu_passport_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_passport_number` `Keywords_bulgaria_eu_passport_number` 찾거나 찾은 경우

```xml
      <!-- Bulgaria Passport Number -->
      <Entity id="f7172b82-c588-4216-845e-4e54e397f29a" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_bulgaria_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_bulgaria_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>키워드

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_bulgaria_eu_passport_number"></a>Keywords_bulgaria_eu_passport_number

- номер на паспорта
- номер на паспорт
- паспорт No

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 문제의 날짜
- 만료 날짜

## <a name="canada-bank-account-number"></a>캐나다 은행 계좌 번호

### <a name="format"></a>형식

7자리 또는 12자리 숫자

### <a name="pattern"></a>패턴

캐나다 은행 계좌 번호는 7자리 또는 12자리입니다.

캐나다 은행 계좌 송금 번호:
- 5자리 숫자
- 하이픈
- 3자리 숫자 OR
- 0 "0"
- 8자리 숫자

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- Regex_canada_bank_account_number 정규식이 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_canada_bank_account_number의 키워드가 발견되었습니다.
- Regex_canada_bank_account_transit_number 정규식이 해당 패턴과 일치하는 콘텐츠를 찾습니다.

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
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

### <a name="format"></a>형식

지역마다 다름

### <a name="pattern"></a>패턴

다양한 패턴에 대한 다국어:
- 앨버타
- British Columbia
- 매니토바
- New Brunswick
- Newfoundland/Labrador
- Nova Scotia
- 오타리오
- Prince Edward Island
- 퀘벡
- Saskatchewan

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
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

#### <a name="keyword_province_name_drivers_license_name"></a>Keyword_[province_name]_drivers_license_name

- 시/도 약어(예: AB)
- 시/도 이름(예: 앨버타)

#### <a name="keyword_canada_drivers_license"></a>Keyword_canada_drivers_license

- DL
- DLS
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
- DriversLicence
- DriversLicences
- DriversLicense
- DriversLicenses
- Drivers Lic
- Drivers Lics
- Drivers License
- Drivers Licenses
- Drivers Licence
- Drivers Licences
- Driver'Lic
- Driver'Lics
- Driver'License
- Driver'Licenses
- Driver'Licence
- Driver'Licences
- Driver'Lic
- Driver' Lics
- Driver' License
- Driver'Licenses
- Driver'Licence
- Driver'Licences
- Driver'sLic
- Driver'sLics
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
- ids
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
- identification
- DL #
- DLS #
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
- DriversLicense #
- DriversLicenses #
- DriversLicence #
- DriversLicences #
- Drivers Lic#
- Drivers Lics#
- Drivers License#
- Drivers Licenses#
- Drivers Licence#
- Drivers Licences#
- Driver'Lic #
- Driver'Lics #
- Driver'License #
- Driver'Licenses #
- Driver'Licence #
- Driver'Licences #
- Driver' Lic#
- Driver' Lics#
- Driver' License#
- Driver' Licenses#
- Driver' Licence#
- Driver' Licences#
- Driver'sLic #
- Driver'sLics #
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
- id #
- ids #
- idcard card#
- idcard cards#
- idcard #
- identification card#
- identification cards#
- identification #


## <a name="canada-health-service-number"></a>캐나다 보건 서비스 번호

### <a name="format"></a>형식

 10자리 숫자

### <a name="pattern"></a>패턴

10자리 숫자

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
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
- disability


## <a name="canada-passport-number"></a>캐나다 여권 번호

### <a name="format"></a>형식

대문자 2자, 6자리 숫자

### <a name="pattern"></a>패턴

대문자 2자, 6자리 숫자

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- Regex_canada_passport_number 정규식이 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- 또는 Keyword_canada_passport_number Keyword_passport 키워드가 발견됩니다.

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
- Passport #
- PassportID
- Passportno
- passportnumber
- パスポート
- パスポート番号
- のストトのNum
- パスポート＃
- Numéro de passeport
- Passeport n °
- Passeport Non
- Passeport #
- Passeport #
- PasseportNon
- Passeportn °


## <a name="canada-personal-health-identification-number-phin"></a>캐나다 PHIN(개인 건강 식별 번호)

### <a name="format"></a>형식

9자리 숫자

### <a name="pattern"></a>패턴

9자리 숫자

### <a name="checksum"></a>체크섬

아니요

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- Regex_canada_phin 정규식이 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- 두 개 이상의 Keyword_canada_phin 또는 Keyword_canada_provinces 발견됩니다.

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
- 오타리오
- British Columbia
- 앨버타
- Saskatchewan
- 매니토바
- Yukon
- Newfoundland and Labrador
- New Brunswick
- Nova Scotia
- Prince Edward Island
- 캐나다


## <a name="canada-social-insurance-number"></a>캐나다 사회 보험 번호

### <a name="format"></a>형식

선택적 하이픈 또는 공백이 있는 9자리 숫자

### <a name="pattern"></a>패턴

서식 있는 형식:
- 3자리 숫자
- 하이픈 또는 공백
- 3자리 숫자
- 하이픈 또는 공백
- 3자리 숫자

무형: 9자리 숫자

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- Func_canadian_sin 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- 다음 패턴 중 두 개 이상
    - Keyword_sin의 키워드가 발견되었습니다.
    - Keyword_sin_collaborative의 키워드가 발견되었습니다.
    - Func_eu_date 함수가 올바른 날짜 형식의 날짜를 찾습니다.
- 체크섬이 통과됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
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
- sins
- ssn
- ssns
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
- Birthday
- Date of Birth


## <a name="chile-identity-card-number"></a>칠레 ID 카드 번호

### <a name="format"></a>형식

7-8자리 숫자와 검사 숫자 또는 문자를 더한 값

### <a name="pattern"></a>패턴

7-8자리 숫자와 함께하는 데 10자리 숫자를 더한 값:
- 1-2자리 숫자
- 선택적 기간
- 3자리 숫자
- 선택적 기간
- 3자리 숫자
- 대시
- 검사 숫자인 1자리 숫자 또는 문자(대소문자 구분 안 )입니다.

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이 Func_chile_id_card 패턴과 일치하는 콘텐츠를 검색합니다.
- 검색된 Keyword_chile_id_card 발견됩니다.
- 체크섬이 통과됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 이 Func_chile_id_card 패턴과 일치하는 콘텐츠를 검색합니다.
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

- cédula de identidad
- identificación
- national identification
- national identification number
- national id
- número de identificación nacional
- rol único nacional
- rol único tributario
- RUN
- RUT
- tarjeta de identificación
- Rol Unico Nacional
- Rol Unico Tributario
- RUN #
- RUT #
- nationaluniqueroleID #
- nacional identidad
- número identificación
- identidad número
- numero identificacion
- identidad numero
- 칠레 ID no.
- 칠레 ID 번호
- 칠레 ID #
- 고유 세금 레지스트리
- 고유 트리부타리 역할
- 고유 세금 역할
- 고유 트리부타리 번호
- 고유 국가 번호
- 고유 국가 역할
- 국가 고유 역할
- 칠레 ID no.
- 칠레 ID 번호
- 칠레 ID #
- R.U.T
- R.U.N


## <a name="china-resident-identity-card-prc-number"></a>중국 거주자 ID 카드(PRC) 번호

### <a name="format"></a>형식

18자리 숫자

### <a name="pattern"></a>패턴

18자리 숫자:
- 주소 코드인 6자리 숫자
- 생년월일인 YYYYMMDD 형식의 8자리 숫자
- 주문 코드인 3자리 숫자
- 검사 숫자인 1자리 숫자

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이 Func_china_resident_id 패턴과 일치하는 콘텐츠를 검색합니다.
- 검색된 Keyword_china_resident_id 발견됩니다.
- 체크섬이 통과됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 이 Func_china_resident_id 패턴과 일치하는 콘텐츠를 검색합니다.
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
- PRC
- National Identification Card
- 身份证
- 居民 身份证
- 居民身份证
- 鉴定
- 身分證
- 居民 身份證
- 鑑定


## <a name="credit-card-number"></a>신용 카드 번호

### <a name="format"></a>형식

서식이 지정되거나 서식이 없는 14-19자리 숫자(dddddd) Luhn 테스트를 통과해야 합니다.

### <a name="pattern"></a>패턴

Visa, MasterCard, Discover Card, JCB, American Express, 기프트 카드, 다이너 카드, Rupay 및 China UnionPay를 비롯한 전 세계 모든 주요 브랜드의 카드를 검색합니다.

### <a name="checksum"></a>체크섬

예, Luhn 검사

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- Func_credit_card 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- 다음 중 하나가 충족됩니다.
    - Keyword_cc_verification의 키워드가 발견되었습니다.
    - Keyword_cc_name의 키워드가 발견되었습니다.
    - Func_expiration_date 함수가 올바른 날짜 형식의 날짜를 찾습니다.
- 체크섬이 통과됩니다.

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있다는 신뢰도는 낮습니다.
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
- 
cód. segurança
- cod. seguranca

- cod. segurança

- cód. seguranca
- cód segurança
- cod seguranca
- cod segurança
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
- validade
- valor
- vencimento
- transaction
- transaction number
- 참조 번호
- セキュリティコード
- セキュリティ コード
- セキュリティナンバー
- セキュリティ ナンバー
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
- 마스터 카드
- master cards
- diner's Club
- diners club
- dinersclub
- discover
- discover card
- discovercard
- discover cards
- JCB
- BrandSmart
- japanese card bureau
- carte blanche
- carteblanche
- credit card
- cc #
- cc#:
- expiration date
- exp date
- expiry date
- date d’expiration
- date d'exp
- date expiration
- bank card
- bankcard
- card number
- card num
- cardnumber
- cardnumbers
- card numbers
- creditcard
- credit cards
- creditcards
- ccn
- card holder
- cardholder
- card holders
- cardholders
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
- Cardmember Acct
- cardmember 계정
- Cardno
- 회사 카드
- 회사 카드
- 카드 유형
- card account number
- card member account
- Cardmember Acct.
- card no.
- card no
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
- carta di credito
- carta credito
- n. carta
- n carta
- nr. carta
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
- nº. do cartão
- no do cartão
- no do cartao
- 아니요. do cartão
- no. do cartao

- rupay
- union pay
- unionpay
- diner's
- diners
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
- アメリカン エクスプレス
- Visa visa visa visa
- Visa의 ೺
- マスターカード
- マスター カード
- マスター
- ダイナースクラブ
- ダイナース クラブ
- ダイナース
- 有効期限
- 期限
- キャッシュカード
- キャッシュ カード
- カード名義人
- カードの名義人
- カードの名義
- デビット カード
- デビットカード
- 中国银联
- 银联



## <a name="croatia-drivers-license-number"></a>크로아티아 운전 면허 번호

### <a name="format"></a>형식

공백 및 디지타이터가 없는 8자리 숫자

### <a name="pattern"></a>패턴

8자리 숫자

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.

- `Regex_croatia_eu_driver's_license_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를 `Keywords_eu_driver's_license_number` `Keywords_croatia_eu_driver's_license_number` 찾거나 찾은 경우

```xml
      <!-- Croatia Driver's License Number -->
      <Entity id="005b3ef1-47dd-4e68-bb02-c6db484d00f2" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_croatia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv 라이선스
- driv 라이선스
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl 번호


#### <a name="keywords_croatia_eu_drivers_license_number"></a>Keywords_croatia_eu_driver s_license_number

- vozačka dozvola
- vozačke dozvole


## <a name="croatia-identity-card-number"></a>크로아티아 ID 카드 번호
이 엔터티는 EU 국가 식별 번호 중요한 정보 유형에 포함됩니다. 독립 실행형 중요한 정보 유형 엔터티로 사용할 수 있습니다.

### <a name="format"></a>형식

9자리 숫자

### <a name="pattern"></a>패턴

9자리 연속 숫자

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 이 Func_croatia_id_card 일치하는 콘텐츠를 검색합니다.
- 검색된 Keyword_croatia_id_card 발견됩니다.

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

- majstorski broj građana
- 마스터 시민 번호
- nacionalni identifikacijski broj
- national identification number
- oib #
- oib
- osobna iskaznica
- osobni id
- osobni identifikacijski broj
- 개인 식별 번호
- porezni broj
- porezni identifikacijski broj
- tax id
- tax identification no
- tax identification number
- tax no #
- tax no
- tax number
- tax registration number
- 에 대한 나타 #
- 일자 #
- 일자 수 #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #


## <a name="croatia-passport-number"></a>크로아티아 여권 번호

### <a name="format"></a>형식

공백 및 디지타이터가 없는 9자리 숫자

### <a name="pattern"></a>패턴

9자리 숫자

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- `Regex_croatia_eu_passport_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_passport_number` `Keywords_croatia_eu_passport_number` 찾거나 찾은 경우
- `Regex_eu_passport_date1`정규식이 DD.MM.YYYY 형식의 날짜를 찾거나 키워드를 `Keywords_eu_passport_date` 찾은 경우

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- `Regex_croatia_eu_passport_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_passport_number` `Keywords_croatia_eu_passport_number` 찾거나 찾은 경우

```xml
      <!-- Croatia Passport Number -->
      <Entity id="7d7a729d-32d8-4204-8d01-d5e6a6c25581" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_croatia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_croatia_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>키워드

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_croatia_eu_passport_number"></a>Keywords_croatia_eu_passport_number

- broj putovnice
- br. Putovnice
- br putovnice

## <a name="croatia-personal-identification-oib-number"></a>크로아티아 개인 식별(OIB) 번호

### <a name="format"></a>형식

11자리 숫자

### <a name="pattern"></a>패턴

11자리 숫자:
- 10자리 숫자
- 마지막 숫자는 검사 숫자입니다.

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이 Func_croatia_oib_number 패턴과 일치하는 콘텐츠를 검색합니다.
- 검색된 Keywords_croatia_eu_tax_file_number 발견됩니다.
- 체크섬이 통과됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 이 Func_croatia_oib_number 패턴과 일치하는 콘텐츠를 검색합니다.
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

- majstorski broj građana
- 마스터 시민 번호
- nacionalni identifikacijski broj
- national identification number
- oib #
- oib
- osobna iskaznica
- osobni id
- osobni identifikacijski broj
- 개인 식별 번호
- porezni broj
- porezni identifikacijski broj
- tax id
- tax identification no
- tax identification number
- tax no #
- tax no
- tax number
- tax registration number
- 에 대한 나타 #
- 일자 #
- 일자 수 #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #

## <a name="cyprus-drivers-license-number"></a>키프로스 드라이버 라이선스 번호

### <a name="format"></a>형식

공백 및 디지타이터가 없는 12자리 숫자

### <a name="pattern"></a>패턴

12자리 숫자

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- `Regex_cyprus_eu_driver's_license_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_driver's_license_number` `Keywords_cyprus_eu_driver's_license_number` 찾거나 찾은 경우

```xml
      <!-- Cyprus Driver's License Number -->
      <Entity id="356fa104-f9ac-4aff-a0e4-2e6e65ea06c4" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv 라이선스
- driv 라이선스
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl 번호

#### <a name="keywords_cyprus_eu_drivers_license_number"></a>Keywords_cyprus_eu_driver s_license_number

- άδεια οδήγησης
- αριθμό άδειας οδήγησης
- άδειες οδήγησης


## <a name="cyprus-identity-card"></a>키프로스 ID 카드
이 중요한 정보 유형은 다음에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거버넌스
- 레코드 관리
- Microsoft 클라우드 앱 보안

### <a name="format"></a>형식

공백 및 디지타이터가 없는 10자리 숫자

### <a name="pattern"></a>패턴

10자리 숫자

### <a name="checksum"></a>체크섬

해당 없음

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- `Regex_cyprus_eu_national_id_card`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 시작  `Keywords_cyprus_eu_national_id_card` 키워드가 발견됩니다.

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

- id card number
- ID 카드 번호
- kimlik karti
- national identification number
- 개인 ID 번호
- ταυτοτητασ


## <a name="cyprus-passport-number"></a>키프로스 여권 번호

### <a name="format"></a>형식

1개 문자와 공백이나 따로 6-8자리 숫자(공백 또는 따로 문자 없음)

### <a name="pattern"></a>패턴

1개의 문자와 6-8자리 숫자

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- `Regex_cyprus_eu_passport_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_passport_number` `Keywords_cyprus_eu_passport_number` 찾거나 찾은 경우
- `Regex_cyprus_eu_passport_date`정규식이 DD/MM/YYYY 형식의 날짜를 찾거나 키워드를 `Keywords_cyprus_eu_passport_date` 찾은 경우

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- `Regex_cyprus_eu_passport_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_passport_number` `Keywords_cyprus_eu_passport_number` 찾거나 찾은 경우

```xml
      <!-- Cyprus Passport Number -->
      <Entity id="9193e2e8-7f8c-43c1-a274-ac40d651936f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_cyprus_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_cyprus_eu_passport_date" />
            <Match idRef="Keywords_cyprus_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_cyprus_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_cyprus_eu_passport_number"></a>Keywords_cyprus_eu_passport_number

- αριθμό διαβατηρίου
- pasaportu
- Αριθμός Διαβατηρίου
- κυπριακό διαβατήριο
- διαβατήριο #
- διαβατήριο
- αριθμός διαβατηρίου
- Pasaport Kimliği
- pasaport numarası
- Pasaport no.
- Αρ. Διαβατηρίου

#### <a name="keywords_cyprus_eu_passport_date"></a>Keywords_cyprus_eu_passport_date

- 만료 날짜
- issued on


## <a name="cyprus-tax-identification-number"></a>키프로스 세금 ID 번호
이 중요한 정보 유형은 다음에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거버넌스
- 레코드 관리
- Microsoft 클라우드 앱 보안

### <a name="format"></a>형식

지정된 패턴의 8자리 숫자와 한 문자

### <a name="pattern"></a>패턴

8자리 숫자와 문자 1자:

- "0" 또는 "9"
- 7자리 숫자
- 한 문자(대소문자 구분 안 )

### <a name="checksum"></a>체크섬

해당 없음

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이  `Func_cyprus_eu_tax_file_number` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 시작  `Keywords_cyprus_eu_tax_file_number` 키워드가 발견됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 이  `Func_cyprus_eu_tax_file_number` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.

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
- tax identification code
- tax identification no
- tax identification number
- tax no #
- tax no
- tax number
- tax registration number
- 에 대한 나타 #
- 일자 #
- 일자 수 #
- taxno #
- taxnumber #
- taxnumber
- tic #
- tic
- tin id
- tin no
- tin #
- vergi kimlik kodu
- vergi kimlik numarası
- αριθμός φορολογικού μητρώου
- κωδικός φορολογικού μητρώου
- φορολογική ταυτότητα
- φορολογικού κωδικού


## <a name="czech-drivers-license-number"></a>체코 운전 면허 번호

### <a name="format"></a>형식

2개의 문자와 6자리 숫자

### <a name="pattern"></a>패턴

8개의 문자 및 숫자:

- 'E' 문자(대소문자 구분 안 )
- 문자
- 공백(선택 사항)
- 6자리 숫자

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- `Regex_czech_republic_eu_driver's_license_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_driver's_license_number` `Keywords_czech_republic_eu_driver's_license_number` 찾거나 찾은 경우

```xml
      <Entity id="86b40d3b-d8ea-4c36-aab0-ef9416a6769c" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>

```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv 라이선스
- driv 라이선스
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl 번호

#### <a name="keywords_czech_republic_eu_drivers_license_number"></a>Keywords_czech_republic_eu_driver s_license_number

- řidičský prúkaz
- řidičské průkazy
- číslo řidičského průkazu
- čísla řidičských průkazů


## <a name="czech-passport-number"></a>체코 여권 번호

### <a name="format"></a>형식

공백이나 디지타이터가 없는 8자리 숫자

### <a name="pattern"></a>패턴

공백이나 디지타이터가 없는 8자리 숫자

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- `Regex_czech_republic_eu_passport_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_passport_number` `Keywords_czech_republic_eu_passport_number` 찾거나 찾은 경우
- `Regex_eu_passport_date1`정규식이 DD.MM.YYYY 형식의 날짜를 찾거나 키워드를 `Keywords_eu_passport_date` 찾은 경우

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- `Regex_czech_republic_eu_passport_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_passport_number` `Keywords_czech_republic_eu_passport_number` 찾거나 찾은 경우

```xml
      <!-- Czech Republic Passport Number -->
      <Entity id="7bcd8ce8-5e92-4bbe-bc92-fa669f0369fa" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_czech_republic_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_czech_republic_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_czech_republic_eu_passport_number"></a>Keywords_czech_republic_eu_passport_number

- cestovní pas
- číslo pasu
- cestovní pasu
- passeport no
- čísla pasu

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 문제의 날짜
- 만료 날짜


## <a name="czech-personal-identity-number"></a>체코 개인 ID 번호

### <a name="format"></a>형식

선택적 슬래시(이전 형식)가 있는 9자리 숫자(선택적 슬래시(새 형식)가 있는 10자리 숫자

### <a name="pattern"></a>패턴

9자리 숫자(이전 형식):
- 생년월일을 나타내는 6자리 숫자
- 선택적 슬래시
- 3자리 숫자

10자리 숫자(새 형식):
- 생년월일을 나타내는 6자리 숫자
- 선택적 슬래시
- 마지막 숫자가 검사 숫자인 4자리 숫자

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.

- 이 Func_czech_id_card 일치하는 콘텐츠를 검색합니다.
- 검색된 Keyword_czech_id_card 발견됩니다.
- 체크섬이 통과됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.

- 이 Func_czech_id_card_new_format 일치하는 콘텐츠를 검색합니다.
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

- birth number
- 체코 공화국 ID
- czechidno #
- daňové číslo
- identifikační číslo
- IDENTITY no
- ID 번호
- identityno #
- identityno
- insurance number
- national identification number
- nationalnumber #
- national number
- osobní číslo
- personalidnumber #
- 개인 ID 번호
- 개인 식별 번호
- personal number
- pid #
- pid
- pojištění číslo
- rč
- rodne cislo
- rodné číslo
- ssn
- ssn #
- social security number
- tax id
- tax identification no
- tax identification number
- tax no #
- tax no
- tax number
- tax registration number
- 에 대한 나타 #
- 일자 #
- 일자 수 #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #
- 고유 ID 번호


## <a name="denmark-drivers-license-number"></a>덴마크 운전 면허 번호

### <a name="format"></a>형식

공백 및 디지타이터가 없는 8자리 숫자

### <a name="pattern"></a>패턴

8자리 숫자

### <a name="checksum"></a>체크섬

아니요

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- `Regex_denmark_eu_driver's_license_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_driver's_license_number` `Keywords_denmark_eu_driver's_license_number` 찾거나 찾은 경우

```xml
      <!-- Denmark Driver's License Number -->
      <Entity id="98a95812-6203-451a-a220-d39870ebef0e" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_denmark_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv 라이선스
- driv 라이선스
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl 번호

#### <a name="keywords_denmark_eu_drivers_license_number"></a>Keywords_denmark_eu_driver s_license_number

- kørekort
- kørekortnummer


## <a name="denmark-passport-number"></a>덴마크 여권 번호

### <a name="format"></a>형식

공백 및 디지타이터가 없는 9자리 숫자

### <a name="pattern"></a>패턴

9자리 숫자

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- `Regex_denmark_eu_passport_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_passport_number` `Keywords_denmark_eu_passport_number` 찾거나 찾은 경우
- 정규식이 DD MM YY 형식의 날짜 또는 `Regex_eu_passport_date2` 검색한 키워드를 `Keywords_eu_passport_date` 찾은 경우

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- `Regex_denmark_eu_passport_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_passport_number` `Keywords_denmark_eu_passport_number` 찾거나 찾은 경우

```xml
      <!-- Denmark Passport Number -->
      <Entity id="25e8c47e-e6fe-4884-a211-74898f8c0196" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_denmark_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date2" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_denmark_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>

```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_denmark_eu_passport_number"></a>Keywords_denmark_eu_passport_number

- pasnummer
- Passeport n°
- pasnumre

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 문제의 날짜
- 만료 날짜


## <a name="denmark-personal-identification-number"></a>덴마크 개인 식별 번호

### <a name="format"></a>형식

하이픈을 포함하는 10자리 숫자

### <a name="pattern"></a>패턴

10자리 숫자:
- 생년월일인 DDMMYY 형식의 6자리 숫자
- 선택적 공백 또는 하이픈
- 마지막 숫자가 검사 숫자인 4자리 숫자

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 정규식 Func_denmark_eu_tax_file_number 일치하는 콘텐츠를 검색합니다.
- 검색된 Keyword_denmark_id 발견됩니다.
- 체크섬이 통과됩니다.

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있다는 신뢰도는 낮습니다.
- 정규식 Func_denmark_eu_tax_file_number 일치하는 콘텐츠를 검색합니다.
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

- centrale personregister
- civilt registreringssystem
- cpr
- cpr #
- gesundheitskarte nummer
- gesundheitsversicherungkarte nummer
- health card
- health insurance card number
- health insurance number
- identification number
- identifikationsnummer
- identifikationsnummer #
- ID 번호
- krankenkassennummer
- nationalid #
- nationalnumber #
- national number
- personalidnumber #
- personalidentityno #
- 개인 ID 번호
- personnummer
- personnummer #
- reisekrankenversicherungskartenummer
- rejsesygesikringskort
- ssn
- ssn #
- 일자 ID
- skat kode
- nummer
- 텐ummer
- social security number
- sundhedsforsikringskort
- sundhedsforsikringsnummer
- sundhedskort
- sundhedskortnummer
- sygesikring
- sygesikringkortnummer
- tax code
- travel health insurance card
- uniqueidentityno #
- tax number
- tax registration number
- tax id
- tax identification number
- 에 대한 나타 #
- taxnumber #
- tax no
- taxno #
- taxnumber
- tax identification no
- tin #
- 일자 #
- 일자 수 #
- tax no #
- tin id
- tin no
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


## <a name="drug-enforcement-agency-dea-number"></a>DEA(마약 집행 기구) 번호

### <a name="format"></a>형식

2개의 문자와 7자리 숫자

### <a name="pattern"></a>패턴

패턴에는 다음이 모두 포함되어야 합니다.
- 등록자 코드인 abcdefghjklmnprstux와 같은 가능한 문자 집합에서 한 문자(대/소문자 구분 안 )를 사용할 수 있습니다.
- 한 문자(대/소문자 구분 안 )는 등록 기관의 성 또는 숫자 '9'의 첫 번째 문자입니다.
- 7자리 숫자( 마지막 숫자는 검사 숫자)

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- Func_dea_number 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- 키워드를 `Keyword_dea_number` 찾은 경우
- 체크섬이 통과됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- Func_dea_number 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- 체크섬이 통과됩니다.

```xml
    <!-- DEA Number -->
    <Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_dea_number" />
      </Pattern>
      <Version minEngineVersion="15.20.1207.000" maxEngineVersion="15.20.3134.000">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_dea_number" />
        </Pattern>
      </Version>
      <Version minEngineVersion="15.20.3135.000">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_dea_number" />
          <Match idRef="Keyword_dea_number" />
        </Pattern>
      </Version>
    </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_dea_number"></a>Keyword_dea_number

- dea
- dea #
- 마약 집행 관리
- 마약 집행 기관


## <a name="estonia-drivers-license-number"></a>에스토니아 운전 면허 번호

### <a name="format"></a>형식

2개의 문자와 6자리 숫자

### <a name="pattern"></a>패턴

2개의 문자와 6자리 숫자:

- 문자 "ET"(대소문자를 구분하지 않습니다.)
- 6자리 숫자

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- `Regex_estonia_eu_driver's_license_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_driver's_license_number` `Keywords_estonia_eu_driver's_license_number` 찾거나 찾은 경우

```xml
      <!-- Estonia Driver's License Number -->
      <Entity id="51da8171-da70-4cc1-9d65-055a59ca4f83" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_estonia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv 라이선스
- driv 라이선스
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl 번호

#### <a name="keywords_estonia_eu_drivers_license_number"></a>Keywords_estonia_eu_driver s_license_number

- permis de conduire
- juhilubade numbrid
- juhiloa number
- 주히루바

## <a name="estonia-personal-identification-code"></a>에스토니아 개인 식별 코드

이 중요한 정보 유형은 다음에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거버넌스
- 레코드 관리
- Microsoft 클라우드 앱 보안

### <a name="format"></a>형식

공백 및 디지타이터가 없는 11자리 숫자

### <a name="pattern"></a>패턴

11자리 숫자:

- 성 및 생년월일(홀수 남성, 1-2세대, 19세, 3-4: 20 세기, 5-6: 21 세기)에 해당하는 1자리 숫자
- 생년월일(YYMMDD)에 해당하는 6자리 숫자
- 같은 날짜에 태어나는 사람을 구분하는 일련 번호에 해당하는 3자리 숫자
- 검사 숫자 1개

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이  `Func_estonia_eu_national_id_card` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 시작  `Keywords_estonia_eu_national_id_card` 키워드가 발견됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 이  `Func_estonia_eu_national_id_card` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.

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
- maksukohustuslase identifitseerimisnumber
- maksunumber
- national identification number
- national number
- 개인 코드
- 개인 ID 번호
- 개인 식별 코드
- 개인 식별 번호
- personalidnumber #
- tax id
- tax identification no
- tax identification number
- tax no #
- tax no
- tax number
- tax registration number
- 에 대한 나타 #
- 일자 #
- 일자 수 #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #


## <a name="estonia-passport-number"></a>에스토니아 여권 번호

### <a name="format"></a>형식

공백이나 따로 7자리 숫자를 입력하고 공백이나 따로 문자를 1개씩 입력합니다.

### <a name="pattern"></a>패턴

한 문자와 7자리 숫자

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- `Regex_estonia_eu_passport_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_passport_number` `Keywords_estonia_eu_passport_number` 찾거나 찾은 경우
- `Regex_eu_passport_date1`정규식이 DD.MM.YYYY 형식의 날짜를 찾거나 키워드를 `Keywords_eu_passport_date` 찾은 경우

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- `Regex_estonia_eu_passport_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_passport_number` `Keywords_estonia_eu_passport_number` 찾거나 찾은 경우

```xml
      <!-- Estonia Passport Number -->
      <Entity id="61f7073a-509e-425b-a754-bc01bb5d5b8c" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_estonia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_estonia_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_estonia_eu_passport_number"></a>Keywords_estonia_eu_passport_number

eesti kodaniku passi number passinumbrid document number document no dokumendi nr

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 문제의 날짜
- 만료 날짜


## <a name="eu-debit-card-number"></a>유럽 직불 카드 번호

### <a name="format"></a>형식

16자리 숫자

### <a name="pattern"></a>패턴

복잡하고 강력한 패턴

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
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
- cc #

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
- cardholder
- cardholders
- cardnumber
- cardnumbers
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
- creditcard
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
- discover
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
- 마스터 카드
- mc
- mister cash
- n carta
- carta
- no de tarjeta
- no do cartao
- no do cartão
- no. de tarjeta

- no. do cartao

- no. do cartão

- nr carta
- nr. carta

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
- nº. do cartão

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
- solo
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
- v-pay
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
- no. dell'edizione

- no. di sicurezza

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
- expiration
- 만료
- expires
- expiry
- fecha de expiracion
- fecha de venc
- gultig bis
- gultigkeitsdatum
- gültig bis
- gültigkeitsdatum
- la scadenza
- scadenza
- valable
- validade
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

이러한 엔터티는 EU 운전 면허 번호에 있으며 중요한 정보 유형입니다.

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
- [룩세부르크](#luxemburg-drivers-license-number)
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


## <a name="eu-national-identification-number"></a>EU 국가 ID 번호

이러한 엔터티는 EU 국가 식별 번호에 있으며 중요한 정보 유형입니다.

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
- [룩세부르크](#luxemburg-national-identification-number-natural-persons)
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

이러한 엔터티는 EU 여권 번호에 있으며 중요한 정보 유형입니다. 이러한 엔터티는 EU 여권 번호 번들에 있습니다.

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
- [룩세부르크](#luxemburg-passport-number)
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


## <a name="eu-social-security-number-or-equivalent-identification"></a>EU 사회 보장 번호 또는 동등한 식별

EU 사회 보장 번호 또는 이와 동등한 식별에 있는 이러한 엔터티는 중요한 정보 유형입니다.

- [오스트리아](#austria-social-security-number)
- [벨기에](#belgium-national-number)
- [크로아티아](#croatia-personal-identification-oib-number)
- [체코어](#czech-personal-identity-number)
- [덴마크](#denmark-personal-identification-number)
- [핀란드](#finland-national-id)
- [프랑스](#france-social-security-number-insee)
- [독일](#germany-identity-card-number)
- [그리스](#greece-national-id-card)
- [헝가리](#hungary-social-security-number-taj)
- [포르투갈](#portugal-citizen-card-number)
- [스페인](#spain-social-security-number-ssn)
- [스웨덴](#sweden-national-id)


## <a name="eu-tax-identification-number"></a>EU 세금 식별 번호

이러한 엔터티는 EU 세금 식별 번호 중요한 정보 유형에 있습니다.

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
- [룩세부르크](#luxemburg-national-identification-number-non-natural-persons)
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

### <a name="format"></a>형식

하이픈을 포함하는 10자리 숫자

### <a name="pattern"></a>패턴

하이픈을 포함하는 10자리 숫자:

- 6자리 숫자
- 하이픈
- 3자리 숫자
- 숫자 또는 문자

### <a name="checksum"></a>체크섬

아니요

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- `Regex_finland_eu_driver's_license_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_driver's_license_number` `Keywords_finland_eu_driver's_license_number` 찾거나 찾은 경우

```xml
      <!-- Finland Driver's License Number -->
      <Entity id="bb3b27a3-79bd-4ac4-81a7-f9fca3c7d1a7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_finland_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv 라이선스
- driv 라이선스
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl 번호


#### <a name="keywords_finland_eu_drivers_license_number"></a>Keywords_finland_eu_driver s_license_number

- ajokortti
- permis de conduire
- ajokortin numero
- kuljettaja lic.
- körkort
- körkortnummer
- förare lic.
- ajokortit
- ajokortin numerot


## <a name="finland-european-health-insurance-number"></a>핀란드 유럽 의료 보험 번호
이 중요한 정보 유형은 다음에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거버넌스
- 레코드 관리
- Microsoft 클라우드 앱 보안

### <a name="format"></a>형식

20자리 숫자

### <a name="pattern"></a>패턴

20자리 숫자:

- 10자리 숫자 - 8024680246
- 선택적 공백 또는 하이픈
- 10자리 숫자

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- regex Regex_Finland_European_Health_Insurance_Number 패턴과 일치하는 콘텐츠를 검색합니다.
- 검색된 Keyword_Finland_European_Health_Insurance_Number 발견됩니다.

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
- 핀란드어hicnumber #
- finska sjukförsäkringskort
- health card
- health insurance card
- health insurance number
- hälsokort
- sairaanhoitokortin
- sairausvakuutuskortti
- sairausvakuutusnumero
- sjukförsäkring nummer
- sjukförsäkringskort
- suomen sairausvakuutuskortti
- terveyskortti


## <a name="finland-national-id"></a>핀란드 국가 ID

### <a name="format"></a>형식

6자리 숫자와 세 번째 숫자와 검사 숫자를 나타내는 문자

### <a name="pattern"></a>패턴

패턴에는 다음이 모두 포함되어야 합니다.
- 생년월일인 DDMMYY 형식의 6자리 숫자
- century 마커('-', '+' 또는 'a')
- 3자리 개인식별번호
- 검사 숫자인 숫자 또는 문자(대소문자 미지정)

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 함수가 Func_finnish_national_id 일치하는 콘텐츠를 찾을 수 있습니다.
- 검색된 Keyword_finnish_national_id 발견
- 체크 체크 um 통과

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 함수가 Func_finnish_national_id 일치하는 콘텐츠를 찾을 수 있습니다.
- 체크 체크 um 통과

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

- ainutlaatuinen henkilökohtainen tunnus
- henkilökohtainen tunnus
- henkilötunnus
- henkilötunnusnumero #
- henkilötunnusnumero
- hetu
- id no
- id number
- identification number
- identiteetti numero
- ID 번호
- idnumber
- kansallinen henkilötunnus
- kansallisen henkilökortin
- national id card
- national id no.
- personal id
- 개인 ID 코드
- personalidnumber #
- personbeteckning
- personnummer
- social security number
- sosiaaliturvatunnus
- tax id
- tax identification no
- tax identification number
- tax no #
- tax no
- tax number
- tax registration number
- 에 대한 나타 #
- 일자 #
- 일자 수 #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #
- tunnistenumero
- tunnus numero
- tunnusluku
- tunnusnumero
- verokortti
- veronumero
- verotunniste
- verotunnus


## <a name="finland-passport-number"></a>핀란드 여권 번호

이 엔터티는 EU Passport Number 중요한 정보 유형에서 사용할 수 있으며 독립 실행형 중요한 정보 유형 엔터티로 사용할 수 있습니다.

### <a name="format"></a>형식
9개의 문자 및 숫자 조합

### <a name="pattern"></a>패턴
9개의 문자 및 숫자 조합:
- 2개 문자(대소문자 구분 안 )
- 7자리 숫자

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- `Regex_finland_passport_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를 `Keywords_eu_passport_number` `Keyword_finland_passport_number` 찾거나 찾은 경우
- `Regex_eu_passport_date1`정규식이 DD.MM.YYYY 형식의 날짜를 찾거나 키워드를 `Keywords_eu_passport_date` 찾은 경우

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- `Regex_finland_passport_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를 `Keywords_eu_passport_number` `Keyword_finland_passport_number` 찾거나 찾은 경우

```xml
      <!-- Finland Passport Number -->
      <Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_finland_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_finland_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_finland_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>키워드

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keyword_finland_passport_number"></a>Keyword_finland_passport_number

- suomalainen passi
- passin numero
- passin numero. #
- passin numero #
- passin numero.
- passi #
- passi number

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 문제의 날짜
- 만료 날짜

## <a name="france-drivers-license-number"></a>프랑스 운전 면허 번호

이 엔터티는 EU 운전 면허 번호 중요한 정보 유형에서 사용할 수 있으며 독립 실행형 중요한 정보 유형 엔터티로 사용할 수 있습니다.

### <a name="format"></a>형식

12자리 숫자

### <a name="pattern"></a>패턴

비슷한 패턴(예: 프랑스 전화 번호)을 무시하기 위한 유효성 검사 기능을 포함하는 12자리 숫자

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 함수가 Func_french_drivers_license 일치하는 콘텐츠를 검색합니다.
- 검색된 Keyword_french_drivers_license 발견됩니다.

```xml
    <!-- France Driver's License Number -->
    <Entity id="18e55a36-a01b-4b0f-943d-dc10282a1824" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_french_drivers_license" />
        <Match idRef="Keyword_french_drivers_license" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_french_drivers_license"></a>Keyword_french_drivers_license

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv 라이선스
- driv 라이선스
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl 번호
- permis de conduire
- licence number
- license number
- licence numbers
- license numbers
- numéros de licence


## <a name="france-health-insurance-number"></a>프랑스 의료 보험 번호
이 중요한 정보 유형은 다음에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거버넌스
- 레코드 관리
- Microsoft 클라우드 앱 보안

### <a name="format"></a>형식

21자리 숫자

### <a name="pattern"></a>패턴

21자리 숫자:

- 10자리 숫자
- 선택적 공백
- 10자리 숫자
- 선택적 공백
- 숫자


### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- regex Regex_France_Health_Insurance_Number 패턴과 일치하는 콘텐츠를 검색합니다.
- 검색된 Keyword_France_Health_Insurance_Number 발견됩니다.

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

- insurance card
- carte vitale
- carte d'assuré social


## <a name="france-national-id-card-cni"></a>프랑스 국가 ID 카드(CNI)

### <a name="format"></a>형식

12자리 숫자

### <a name="pattern"></a>패턴

12자리 숫자

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있다는 신뢰도는 낮습니다.
- Regex_france_cni 정규식이 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- 검색된 Keywords_france_eu_national_id_card 발견됩니다.

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
- carte nationale d'identité
- carte nationale d'idenite no
- cni #
- cni
- compte bancaire
- national identification number
- national identity
- nationalidno #
- numéro d'assurance maladie
- numéro de carte vitale


## <a name="france-passport-number"></a>프랑스 여권 번호
이 엔터티는 EU 여권 번호 중요한 정보 유형에서 사용할 수 있습니다. 독립 실행형 중요한 정보 유형 엔터티로도 사용할 수 있습니다.

### <a name="format"></a>형식

9자리 숫자 및 문자

### <a name="pattern"></a>패턴

9자리 숫자 및 문자:
- 2자리 숫자
- 2개 문자(대소문자 구분 안 )
- 5자리 숫자

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이 `Func_fr_passport` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를 `Keywords_eu_passport_number` `Keywords_france_eu_passport_number` 찾거나 찾은 경우
- 정규식이 DD MM YYYY 형식의 날짜를 찾거나 `Regex_eu_passport_date3` 키워드를 `Keywords_eu_passport_date` 찾은 경우

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 이 `Func_fr_passport` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를 `Keywords_eu_passport_number` `Keywords_france_eu_passport_number` 찾거나 찾은 경우


```xml
    <!-- France Passport Number -->
    <Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_fr_passport" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_france_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date3" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_fr_passport" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_france_eu_passport_number" />
          </Any>
        </Pattern>
    </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_france_eu_passport_number"></a>Keywords_france_eu_passport_number

- numéro de passeport
- passeport n °
- passeport non
- passeport #
- passeport #
- passeportnon
- passeportn °
- passeport français
- passeport livre
- passeport carte
- numéro passeport
- passeport n°
- n° du passeport
- n° passeport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 문제의 날짜
- 만료 날짜


## <a name="france-social-security-number-insee"></a>프랑스 사회 보장 번호(INSEE)

### <a name="format"></a>형식

15자리 숫자

### <a name="pattern"></a>패턴

다음 두 패턴 중 하나가 일치해야 합니다.
- 13자리 숫자, 공백, 2자리 숫자<br/>
또는
- 15자리 연속 숫자

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이 `Func_french_insee` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- Keyword_fr_insee의 키워드가 발견되었습니다.
- 체크섬이 통과됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 이 Func_french_insee Func_fr_insee 일치하는 콘텐츠를 찾을 수 있습니다.
- 체크섬이 통과됩니다.

```xml
    <!-- France INSEE -->
    <Entity id="71f62b97-efe0-4aa1-aa49-e14de253619d" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_french_insee" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_fr_insee" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Keyword_fr_insee" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_fr_insee"></a>Keyword_fr_insee

- code sécu
- d'identité nationale
- insee
- fssn #
- le numéro d'identification nationale
- le code de la sécurité sociale
- national id
- national identification
- no d'identité
- 
no. d'identité
- numéro d'assurance
- numéro d'identité
- numero d'identite
- numéro de sécu
- numéro de sécurité sociale
- no d'identite
- 
no. d'identite
- ssn
- ssn #
- sécurité sociale
- securité sociale
- securite sociale
- socialsecuritynumber
- social security number
- social security code
- social insurance number


## <a name="france-tax-identification-number"></a>프랑스 세금 식별 번호

### <a name="format"></a>형식

13자리 숫자

### <a name="pattern"></a>패턴

13자리 숫자

- 0, 1, 2 또는 3이 되어야 하는 1자리 숫자
- 1자리 숫자
- 공백 1개(선택 사항)
- 2자리 숫자
- 공백 1개(선택 사항)
- 3자리 숫자
- 공백 1개(선택 사항)
- 3자리 숫자
- 공백 1개(선택 사항)
- 검사 숫자 3개


### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이  `Func_france_eu_tax_file_number` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 시작  `Keywords_france_eu_tax_file_number` 키워드가 발견됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 이  `Func_france_eu_tax_file_number` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.

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

- numéro d'identification 회계
- tax id
- tax identification no
- tax identification number
- tax no #
- tax no
- tax number
- tax registration number
- 에 대한 나타 #
- 일자 #
- 일자 수 #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #


## <a name="france-value-added-tax-number"></a>프랑스 부가가치세 번호
이 중요한 정보 유형은 다음에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거버넌스
- 레코드 관리
- Microsoft 클라우드 앱 보안

### <a name="format"></a>형식

영문자 13자 패턴

### <a name="pattern"></a>패턴

영문자 13자 패턴:

- 두 글자 - FR(대소문자 미지정)
- 선택적 공백 또는 하이픈
- 2개의 문자 또는 숫자
- 선택적 공백, 점, 하이픈 또는 콤보
- 3자리 숫자
- 선택적 공백, 점, 하이픈 또는 콤보
- 3자리 숫자
- 선택적 공백, 점, 하이픈 또는 콤보
- 3자리 숫자

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이 Func_france_value_added_tax_number 패턴과 일치하는 콘텐츠를 검색합니다.
- 검색된 Keywords_france_value_added_tax_number 발견됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 이 Func_france_value_added_tax_number 패턴과 일치하는 콘텐츠를 검색합니다.

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

- vat number
- vat no
- vat #
- 부가가치세
- siren identification no numéro d'identification taxe sur valeur ajoutée
- taxe valeur ajoutée
- taxe sur la valeur ajoutée
- n° tva
- numéro de tva
- numéro d'identification siren


## <a name="germany-drivers-license-number"></a>독일 운전 면허 번호

이 중요한 정보 유형 엔터티는 EU 운전 면허 번호 중요한 정보 유형에 포함됩니다. 독립 실행형 중요한 정보 유형 엔터티로도 사용할 수 있습니다.

### <a name="format"></a>형식

11자리 숫자와 문자 조합

### <a name="pattern"></a>패턴

11자리 숫자 및 문자(대/소문자 구분 안 됨):
- 숫자 또는 문자
- 2자리 숫자
- 6자리 숫자 또는 문자
- 숫자
- 숫자 또는 문자

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- Func_german_drivers_license 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_german_drivers_license_number의 키워드가 발견되었습니다.
- 체크섬이 통과됩니다.

```xml
    <!-- German Driver's License Number -->
    <Entity id="91da9335-1edb-45b7-a95f-5fe41a16c63c" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_drivers_license" />
        <Match idRef="Keyword_german_drivers_license" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_german_drivers_license_number"></a>Keyword_german_drivers_license_number

- ausstellungsdatum
- ausstellungsort
- ausstellende behöde
- ausstellende behorde
- ausstellende behoerde
- führerschein
- fuhrerschein
- fuehrerschein
- führerscheinnummer
- fuhrerscheinnummer
- fuehrerscheinnummer
- führerschein- 
- fuhrerschein- 
- fuehrerschein- 
- führerscheinnummernr
- fuhrerscheinnummernr
- fuehrerscheinnummernr
- führerscheinnummerklasse
- fuhrerscheinnummerklasse
- fuehrerscheinnummerklasse
- nr-führerschein
- nr-fuhrerschein
- nr-fuehrerschein
- no-führerschein
- no-fuhrerschein
- no-fuehrerschein
- n-führerschein
- n-fuhrerschein
- n-fuehrerschein
- permis de conduire
- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv 라이선스
- driv 라이선스
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dlno


## <a name="germany-identity-card-number"></a>독일 ID 카드 번호

### <a name="format"></a>형식

2010년 11월 1일: 9-11개의 문자 및 숫자

1987년 4월 1일부터 2010년 10월 31일까지: 10자리

### <a name="pattern"></a>패턴

2010년 11월 1일 이후: 영문자 패턴 9~11자
- L, M, N, P, R, T, V, W, X, Y(대소문자 미지정)
- C, F, G, H, J, K, L, M, N, P, R, T, V, W, X, Y 및 Z의 8자리 숫자 또는 문자(대소문자 미정)
- 선택적 검사 숫자
- 선택적 d/D

1987년 4월 1일부터 2010년 10월 31일까지:
- 10자리 숫자

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이 `Func_german_id_card_with_check` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 시작 `Keyword_germany_id_card` 키워드가 발견됩니다.
- 체크섬이 통과됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 정규식은 패턴과 일치하는 콘텐츠를 검색합니다(2010년 전에 발급된 검사 숫자가 없는 `Regex_germany_id_card` 9자 또는 posy 2010에서 발급된 10자리 숫자 패턴).
- 검색된 Keyword_germany_id_card 발견됩니다.

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있다는 신뢰도는 낮습니다.
- 이 `Func_german_id_card_with_check` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 체크섬이 통과됩니다.


```xml
      <!-- Germany Identity Card Number -->
      <Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" patternsProximity="300" recommendedConfidence="75"> 
        <Pattern confidenceLevel="75">
         <IdMatch idRef="Regex_germany_id_card" /> 
         <Match idRef="Keyword_germany_id_card" /> 
        </Pattern>
        <Version minEngineVersion="15.20.4545.000"> 
          <Pattern confidenceLevel="85">
           <IdMatch idRef="Func_german_id_card_with_check" />
            <Match idRef="Keyword_germany_id_card" /> 
          </Pattern> 
          <Pattern confidenceLevel="65">
           <IdMatch idRef="Func_german_id_card_with_check" /> 
          </Pattern> 
        </Version>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_germany_id_card"></a>Keyword_germany_id_card

- ausweis
- gpid
- identification
- identifikation
- identifizierungsnummer
- identity card
- ID 번호
- id-nummer
- personal id
- personalausweis
- persönliche id nummer
- persönliche identifikationsnummer
- persönliche-id-nummer


## <a name="germany-passport-number"></a>독일 여권 번호

### <a name="format"></a>형식

9~11자

### <a name="pattern"></a>패턴

- C, F, G, H, J, K(대소문자 미구분)
- C, F, G, H, J, K, L, M, N, P, R, T, V, W, X, Y 및 Z의 8자리 숫자 또는 문자(대소문자 미정)
- 선택적 검사 숫자
- 선택적 d/D

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이 `Func_german_passport_checksum` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를 `Keyword_german_passport` `Keywords_eu_passport_number_common` 찾거나 찾은 경우
- 체크섬이 통과됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 이 `Func_german_passport` 함수는 9자 패턴과 일치하는 콘텐츠를 검색합니다(검사 숫자 및 선택적 d/D).
- 키워드를 `Keyword_german_passport` `Keywords_eu_passport_number_common` 찾거나 찾은 경우

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있다는 신뢰도는 낮습니다.
- 이 `Func_german_passport_checksum` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 체크섬이 통과됩니다.

```xml
    <!-- German Passport Number -->
    <Entity id="2e3da144-d42b-47ed-b123-fbf78604e52c" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_passport" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keywords_eu_passport_number_common" />
        </Any>
      </Pattern>
      <Version minEngineVersion="15.20.4570.0">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_german_passport_checksum" />
          <Any minMatches="1">
            <Match idRef="Keyword_german_passport" />
            <Match idRef="Keywords_eu_passport_number_common" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_german_passport_checksum" />
        </Pattern>
      </Version>
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
- passeport no.
- passeport no

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers


## <a name="germany-tax-identification-number"></a>독일 세금 ID 번호

### <a name="format"></a>형식

공백 및 디지타이터가 없는 11자리 숫자

### <a name="pattern"></a>패턴

11자리 숫자

- 2자리 숫자
- 선택적 공백 1개
- 3자리 숫자
- 선택적 공백 1개
- 3자리 숫자
- 선택적 공백 1개
- 2자리 숫자
- 검사 숫자 1개

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이  `Func_germany_eu_tax_file_number` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 시작  `Keywords_germany_eu_tax_file_number` 키워드가 발견됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 이  `Func_germany_eu_tax_file_number` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.

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
- tax identification no
- tax identification number
- tax no #
- tax no
- tax number
- tax registration number
- 에 대한 나타 #
- 일자 #
- 일자 수 #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #
- zinn #
- zinn
- zinnnummer


## <a name="germany-value-added-tax-number"></a>독일 부가가치세 번호
이 중요한 정보 유형은 다음에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거버넌스
- 레코드 관리
- Microsoft 클라우드 앱 보안

### <a name="format"></a>형식

영문자 11자 패턴

### <a name="pattern"></a>패턴

11자 영문자 패턴:

- 문자 D 또는 d
- E 또는 e 문자
- 선택적 공백
- 3자리 숫자
- 선택적 공백 또는 콤보
- 3자리 숫자
- 선택적 공백 또는 콤보
- 3자리 숫자

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이 Func_germany_value_added_tax_number 일치하는 콘텐츠를 검색합니다.
- 검색된 Keywords_germany_value_added_tax_number 발견됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 이 Func_germany_value_added_tax_number 일치하는 콘텐츠를 검색합니다.

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

- vat number
- vat no
- vat #
- vat# mehrwertsteuer
- mwst
- mehrwertsteuer identifikationsnummer
- mehrwertsteuer nummer


## <a name="greece-drivers-license-number"></a>그리스 운전 면허 번호

이 엔터티는 EU 운전 면허 번호 중요한 정보 유형에 포함됩니다. 독립 실행형 중요한 정보 유형 엔터티로도 사용할 수 있습니다.

### <a name="format"></a>형식

공백 및 디지타이터가 없는 9자리 숫자

### <a name="pattern"></a>패턴

9자리 숫자

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- `Regex_greece_eu_driver's_license_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_driver's_license_number` `Keywords_greece_eu_driver's_license_number` 찾거나 찾은 경우

```xml
      <!-- Greece Driver's License Number -->
      <Entity id="7a2200b5-aacf-4e3c-ab36-136d3e68b7da" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_greece_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv 라이선스
- driv 라이선스
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl 번호


#### <a name="keywords_greece_eu_drivers_license_number"></a>Keywords_greece_eu_driver s_license_number

- δεια οδήγησης
- Adeia odigisis
- Άδεια οδήγησης
- Δίπλωμα οδήγησης


## <a name="greece-national-id-card"></a>그리스 국가 ID 카드

### <a name="format"></a>형식

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

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 정규식 Regex_greece_id_card 일치하는 콘텐츠를 검색합니다.
- 검색된 Keyword_greece_id_card 발견됩니다.

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있다는 신뢰도는 낮습니다.
- 정규식 Regex_greece_id_card 일치하는 콘텐츠를 검색합니다.

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

- 그리스어 ID
- 그리스어 국가 ID
- 그리스어 개인 ID 카드
- 그리스어 경찰 ID
- identity card
- tautotita
- ταυτότητα
- ταυτότητας


## <a name="greece-passport-number"></a>그리스 여권 번호

### <a name="format"></a>형식

문자 2개와 공백이나 따로 7자리 숫자(공백이나 따로 문자 없음)

### <a name="pattern"></a>패턴

2개 문자와 7자리 숫자

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- `Regex_greece_eu_passport_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_passport_number` `Keywords_greece_eu_passport_number` 찾거나 찾은 경우
- `Regex_greece_eu_passport_date`정규식이 DD MMM YY(예 - 28 8월 19일) 형식의 날짜 또는 키워드를 `Keywords_greece_eu_passport_date` 찾음

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- `Regex_greece_eu_passport_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_passport_number` `Keywords_greece_eu_passport_number` 찾거나 찾은 경우

```xml
      <!-- Greece Passport Number -->
      <Entity id="7e65eb47-cdf9-4f52-8f90-2a27d5ee67e3" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_greece_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_greece_eu_passport_date" />
            <Match idRef="Keywords_greece_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_greece_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_greece_eu_passport_number"></a>Keywords_greece_eu_passport_number

- αριθμός διαβατηρίου
- αριθμούς διαβατηρίου
- αριθμός διαβατηριο


## <a name="greece-social-security-number-amka"></a>그리스 AMKA(사회 보장 번호)
이 중요한 정보 유형은 다음에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거버넌스
- 레코드 관리
- Microsoft 클라우드 앱 보안

### <a name="format"></a>형식

공백 및 디지타이터가 없는 11자리 숫자

### <a name="pattern"></a>패턴

- YYMMDD 생년월일로 6자리 숫자
- 4자리 숫자
- 검사 숫자

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이  `Func_greece_eu_ssn` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 시작  `Keywords_greece_eu_ssn_or_equivalent` 키워드가 발견됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 이  `Func_greece_eu_ssn` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.

```xml
      <!-- Greece Social Security Number (AMKA) -->
      <Entity id="e39b03f4-50ea-41ae-af7a-a4b9539596ad" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_greece_eu_ssn" />
          <Match idRef="Keywords_greece_eu_ssn_or_equivalent" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_greece_eu_ssn" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_greece_eu_ssn_or_equivalent"></a>Keywords_greece_eu_ssn_or_equivalent

- ssn
- ssn #
- social security no
- socialsecurityno #
- social security number
- amka
- a.m.k.a.
- Αριθμού Μητρώου Κοινωνικής Ασφάλισης


## <a name="greece-tax-identification-number"></a>그리스 세금 ID 번호
이 중요한 정보 유형은 다음에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거버넌스
- 레코드 관리
- Microsoft 클라우드 앱 보안

### <a name="format"></a>형식

공백 및 디지타이터가 없는 9자리 숫자

### <a name="pattern"></a>패턴

9자리 숫자

### <a name="checksum"></a>체크섬

해당 없음

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.

- `Regex_greece_eu_tax_file_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 시작  `Keywords_greece_eu_tax_file_number` 키워드가 발견됩니다.

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
- φμ|aφμ αριθμός
- aφμ
- tax id
- tax identification no
- tax identification number
- tax no #
- tax no
- tax number
- tax registration number
- tax registry no
- tax registry number
- 에 대한 나타 #
- 일자 #
- 일자 수 #
- taxno #
- taxnumber #
- taxnumber
- taxregistryno #
- tin id
- tin no
- tin #
- αριθμός φορολογικού μητρώου
- τον αριθμό φορολογικού μητρώου
- φορολογικού μητρώου νο


## <a name="hong-kong-identity-card-hkid-number"></a>HKID(홍콩 ID 카드) 번호

### <a name="format"></a>형식

8-9자리 문자 및 숫자와 마지막 문자를 선택적 괄호로 묶어서 조합

### <a name="pattern"></a>패턴

8-9자리 문자 조합:
- 1-2개 문자(대소문자 구분 안 )
- 6자리 숫자
- 검사 숫자에 해당하고 선택적으로 괄호로 묶는 마지막 문자(임의 숫자 또는 문자 A)

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 이 Func_hong_kong_id_card 일치하는 콘텐츠를 검색합니다.
- 검색된 Keyword_hong_kong_id_card 발견됩니다.
- 체크섬이 통과됩니다.

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있다는 신뢰도는 낮습니다.
- 이 Func_hong_kong_id_card 일치하는 콘텐츠를 검색합니다.
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
- 홍콩 ID 카드
- HKIDC
- id card
- identity card
- hk ID 카드
- 홍콩 ID
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


## <a name="hungary-drivers-license-number"></a>헝가리 운전 면허 번호

### <a name="format"></a>형식

2개의 문자와 6자리 숫자

### <a name="pattern"></a>패턴

2개의 문자와 6자리 숫자:

- 2개 문자(대소문자 구분 안 )
- 6자리 숫자

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.

- `Regex_hungary_eu_driver's_license_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_driver's_license_number` `Keywords_hungary_eu_driver's_license_number` 찾거나 찾은 경우

```xml
      <Entity id="9d31c46b-6e6b-444c-aeb1-6dd7e604bb24" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_hungary_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv 라이선스
- driv 라이선스
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl 번호


#### <a name="keywords_hungary_eu_drivers_license_number"></a>Keywords_hungary_eu_driver s_license_number

- vezetoi engedely
- vezetői engedély
- vezetői engedélyek


## <a name="hungary-personal-identification-number"></a>헝가리 개인식별번호
이 중요한 정보 유형은 다음에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거버넌스
- 레코드 관리
- Microsoft 클라우드 앱 보안

### <a name="format"></a>형식

11자리 숫자

### <a name="pattern"></a>패턴

11자리 숫자:

- 성별에 해당하는 1자리 숫자, 남성 1명, 여성 2명입니다. 1900년 이전의 시민이나 시민권이 2배인 시민에 대해 다른 번호가 가능합니다.
- 생년월일(YYMMDD)에 해당하는 6자리 숫자
- 일련 번호에 해당하는 3자리 숫자
- 검사 숫자 1개

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.

- 이  `Func_hungary_eu_national_id_card` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 시작  `Keywords_hungary_eu_national_id_card` 키워드가 발견됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.

- 이  `Func_hungary_eu_national_id_card` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.

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

- id number
- identification number
- sz ig
- sz. ig.
- sz.ig.
- személyazonosító igazolvány
- személyi igazolvány


## <a name="hungary-passport-number"></a>헝가리 여권 번호

### <a name="format"></a>형식

2개의 문자와 공백이나 따로 7자리 숫자(공백이나 따로 문자 없음)

### <a name="pattern"></a>패턴

2개의 문자와 6-7자리 숫자

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- `Regex_hungary_eu_passport_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_passport_number` `Keywords_hungary_eu_passport_number` 찾거나 찾은 경우
- `Regex_hungary_eu_passport_date`정규식이 DD MMM/MMM YY(예 - 01 MÁR/MAR 12) 형식의 날짜를 찾거나 키워드가 `Keywords_eu_passport_date` 발견되었습니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- `Regex_hungary_eu_passport_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_passport_number` `Keywords_hungary_eu_passport_number` 찾거나 찾은 경우

```xml
      <!-- Hungary Passport Number -->
      <Entity id="5b483910-9aa7-4c99-9917-f4001464bda7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_hungary_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_hungary_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_hungary_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>키워드

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_hungary_eu_passport_number"></a>Keywords_hungary_eu_passport_number

- útlevél száma
- Útlevelek száma
- útlevél szám

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 문제의 날짜
- 만료 날짜


## <a name="hungary-social-security-number-taj"></a>헝가리 TAJ(사회 보장 번호)

### <a name="format"></a>형식

공백 및 디지타이터가 없는 9자리 숫자

### <a name="pattern"></a>패턴

9자리 숫자

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.

- 이  `Func_hungary_eu_ssn_or_equivalent` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 시작  `Keywords_hungary_eu_ssn_or_equivalent` 키워드가 발견됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.

- 이  `Func_hungary_eu_ssn_or_equivalent` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.

```xml
      <!-- Hungarian Social Security Number (TAJ) -->
      <Entity id="0de78315-9537-47f5-95ab-b3e77eba3993" patternsProximity="300" recommendedConfidence="85">
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

- 헝가리어 사회 보장 번호
- social security number
- socialsecuritynumber #
- hssn #
- socialsecuritynno
- hssn
- taj
- taj #
- ssn
- ssn #
- social security no
- áfa
- közösségi adószám
- általános forgalmi adó szám
- hozzáadottérték adó
- áfa szám
- magyar áfa szám


## <a name="hungary-tax-identification-number"></a>헝가리 세금 ID 번호
이 중요한 정보 유형은 다음에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거버넌스
- 레코드 관리
- Microsoft 클라우드 앱 보안

### <a name="format"></a>형식

공백이나 디지타이터가 없는 10자리 숫자

### <a name="pattern"></a>패턴

10자리 숫자:

- "8"이 되어야 하는 1자리 숫자
- 8자리 숫자
- 검사 숫자 1개

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.

- 이  `Func_hungary_eu_tax_file_number` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 시작  `Keywords_hungary_eu_tax_file_number` 키워드가 발견됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.

- 이  `Func_hungary_eu_tax_file_number` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.

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

- adóazonosító szám
- adóhatóság szám
- adószám
- 헝가리어 주석
- hungatiantin #
- tax authority no
- tax id
- tax identification no
- tax identification number
- tax no #
- tax no
- tax number
- tax registration number
- 에 대한 나타 #
- 일자 #
- 일자 수 #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #
- vat number


## <a name="hungary-value-added-tax-number"></a>헝가리 부가가치 세금 번호
이 중요한 정보 유형은 다음에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거버넌스
- 레코드 관리
- Microsoft 클라우드 앱 보안

### <a name="format"></a>형식

영문자 10자 패턴

### <a name="pattern"></a>패턴

영문자 10자 패턴:

- 두 글자 - HU 또는 hu
- 선택적 공간
- 8자리 숫자

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.

- 이 Func_hungarian_value_added_tax_number 패턴과 일치하는 콘텐츠를 검색합니다.
- 검색된 Keywords_hungarian_value_added_tax_number 발견됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.

- 이 Func_hungarian_value_added_tax_number 패턴과 일치하는 콘텐츠를 검색합니다.

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
- 부가가치세 번호
- vat #
- vatno #
- hungarianvatno #
- tax no.
- value added tax áfa
- közösségi adószám
- általános forgalmi adó szám
- hozzáadottérték adó
- áfa szám


## <a name="india-drivers-license-number"></a>인도 운전 면허 번호

### <a name="format"></a>형식

영문자 15자 패턴

### <a name="pattern"></a>패턴

15자리 문자 또는 숫자:
- 상태 코드를 나타내는 두 글자
- 선택적 공백 또는 대시
- 도시 코드를 나타내는 2자리 숫자
- 선택적 공백 또는 대시
- 문제 연도 표시 4자리
- 선택적 공백 또는 대시
- 7자리 숫자

### <a name="checksum"></a>체크섬

아니요

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- `Regex_india_driving_license`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 시작 `Keywords_eu_driver's_license_number_common` 키워드가 발견됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- `Regex_india_driving_license`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.


```xml
      <!-- India Driver's License Number -->
        <Entity id="680788a3-53b6-455a-b891-c38cd76dc917" patternsProximity="300" recommendedConfidence="85" relaxProximity="true">
          <Pattern confidenceLevel="85">
            <IdMatch idRef="Regex_india_driving_license" />
            <Match idRef="Keywords_eu_driver's_license_number_common" />
          </Pattern>
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_india_driving_license" />
            </Pattern>
        </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_drivers_license_number_common"></a>Keywords_eu_driver s_license_number_common

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv 라이선스
- driv 라이선스
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl 번호



## <a name="india-gst-number"></a>인도 GST 번호

### <a name="format"></a>형식

영문자 15자 패턴

### <a name="pattern"></a>패턴

15자리 문자 또는 숫자:
- 유효한 상태 코드를 나타내는 두 자리 숫자
- 선택적 공백 또는 대시
- PAN(영구 계정 번호)을 나타내는 10자 
- 한 문자 또는 숫자
- 선택적 공백 또는 대시
- 한 문자 'z' 또는 'Z'
- 선택적 공백 또는 대시
- 검사 숫자 1개

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이 `Func_india_gst_number` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 시작 `Keyword_india_gst_number` 키워드가 발견됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 이 `Func_india_gst_number` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.


```xml
    <!-- India GST number  -->
      <Entity id="9f5a721c-2fd2-446a-a27e-0c02fbe4630c" patternsProximity="300" recommendedConfidence="85" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_india_gst_number" />
          <Match idRef="Keyword_india_gst_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_india_gst_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_india_gst_number"></a>Keyword_india_gst_number

- gst
- gstin
- 상품 및 서비스 세금
- 상품 및 서비스 세금


## <a name="india-permanent-account-number-pan"></a>인도 PAN(영구 계정 번호)

### <a name="format"></a>형식

10자리 문자 또는 숫자

### <a name="pattern"></a>패턴

10자리 문자 또는 숫자:
- 3개의 문자(대소문자 구분 안 )
- C, P, H, F, A, T, B, L, J, G의 문자(대소문자를 구분하지 않습니다)입니다.
- 문자
- 4자리 숫자
- 알파벳 검사 숫자인 문자

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 정규식 Regex_india_permanent_account_number 일치하는 콘텐츠를 검색합니다.
- 검색된 Keyword_india_permanent_account_number 발견됩니다.

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있다는 신뢰도는 낮습니다.
- 정규식 Regex_india_permanent_account_number 일치하는 콘텐츠를 검색합니다.


```xml
      <!-- India Permanent Account Number -->
      <Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_india_permanent_account_number" />
          <Match idRef="Keyword_india_permanent_account_number" />
        </Pattern>
        <Version minEngineVersion="15.20.3520.000">
          <Pattern confidenceLevel="65">
            <IdMatch idRef="Regex_india_permanent_account_number" />
          </Pattern>
        </Version>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_india_permanent_account_number"></a>Keyword_india_permanent_account_number

- Permanent Account Number
- PAN

## <a name="india-unique-identification-aadhaar-number"></a>인도 고유 ID(Aadhaar) 번호

### <a name="format"></a>형식

선택적 공백 또는 대시를 포함하는 12자리 숫자

### <a name="pattern"></a>패턴

12자리 숫자:
- 0 또는 1이 아닌 숫자
- 3자리 숫자
- 선택적 공백 또는 대시 
- 4자리 숫자
- 선택적 공백 또는 대시 
- 검사 숫자인 마지막 숫자

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이 Func_india_aadhaar 일치하는 콘텐츠를 검색합니다.
- 검색된 Keyword_india_aadhar 발견됩니다.
- 체크섬이 통과됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.

- 이 Func_india_aadhaar 일치하는 콘텐츠를 검색합니다.
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
- aadhaar
- aadhar
- aadhar #
- uid
- आधार
- uidai


## <a name="india-voter-id-card"></a>인도 투표자 ID 카드

### <a name="format"></a>형식

영문자 10자 패턴

### <a name="pattern"></a>패턴

10자리 문자 또는 숫자:
- 3개의 문자
- 7자리 숫자

### <a name="checksum"></a>체크섬

아니요

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- `Regex_india_voter_id_card`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 시작 `Keyword_india_voter_id_card` 키워드가 발견됩니다.

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있다는 신뢰도는 낮습니다.
- `Regex_india_voter_id_card`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.


```xml
      <!-- India Voter Id Card  -->
        <Entity id="646d643f-5228-4408-acc8-f2e81a6df897" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
           <Pattern confidenceLevel="75">
             <IdMatch idRef="Regex_india_voter_id_card" />
             <Match idRef="Keyword_india_voter_id_card" />
            </Pattern>
           <Pattern confidenceLevel="65">
              <IdMatch idRef="Regex_india_voter_id_card" />
            </Pattern>
        </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_india_voter_id_card"></a>Keyword_india_voter_id_card

- voter
- voterid
- votercard
- voteridcard
- 선택적 사진 ID 카드
- 도구
- ECI
- 은(는)


## <a name="indonesia-identity-card-ktp-number"></a>인도네시아 ID 카드(KTP) 번호

### <a name="format"></a>형식

선택적으로 마침표를 포함하는 16자리 숫자

### <a name="pattern"></a>패턴

16자리 숫자:
- 2자리 시/도 코드 
- 마침표(옵션) 
- 2자리 지역 또는 구/군/시 코드 
- 2자리 소구역 코드 
- 마침표(옵션) 
- 생년월일인 DDMMYY 형식의 6자리 숫자
- 마침표(옵션) 
- 4자리 숫자

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.

- 정규식 Regex_indonesia_id_card 일치하는 콘텐츠를 검색합니다.
- 검색된 Keyword_indonesia_id_card 발견됩니다.

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

## <a name="international-banking-account-number-iban"></a>IBAN(국제 은행 계좌 번호)

### <a name="format"></a>형식

국가 코드(2문자) 및 검사 숫자(2자리) 및 bban 번호(최대 30자)

### <a name="pattern"></a>패턴

패턴에는 다음이 모두 포함되어야 합니다.

- 2문자 국가 코드
- 검사 숫자 2개(선택적 공백)
- 4개의 문자 또는 숫자로 1-7개 그룹(공백으로 구분할 수 있습니다.
- 1-3 문자 또는 숫자

각 국가에 대한 형식은 약간 다릅니다. IBAN 중요한 정보 유형은 다음 60개 국가에 해당합니다.

- 광고
- ae
- al
- at
- az
- ba
- be
- bg
- bh
- ch
- cr
- cy
- cz
- de
- dk
- do
- ee
- es
- fi
- fo
- fr
- gb
- ge
- gi
- gl
- gr
- hr
- hu
- ie
- il
- is
- it
- kw
- kz
- lb
- li
- lt
- lu
- lv
- mc
- md
- me
- mk
- mr
- mt
- mu
- nl
- 아니요
- pl
- pt
- ro
- rs
- sa
- se
- si
- sk
- sm
- tn
- tr
- vg

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.

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


## <a name="international-classification-of-diseases-icd-10-cm"></a>국제질병 분류(ICD-10-CM)

### <a name="format"></a>형식

사전

### <a name="pattern"></a>패턴

키워드

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 검색된 Dictionary_icd_10_updated 발견됩니다.
- 검색된 Dictionary_icd_10_codes 발견됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 업데이트된 Dictionary_icd_10_ 키워드가 발견되었습니다.

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

ICD-Dictionary_icd_10_updated 국제질병 [분류, 10번째 수정, ICD-10-CM(예방 수정)을](https://go.microsoft.com/fwlink/?linkid=852604)기반으로 하는 키워드 사전의 용어입니다. 이 유형은 보험 코드가 아니라 용어만 됩니다.

ICD-Dictionary_icd_10_codes 국제질병 [분류, 10번째 수정, ICD-10-CM(예방 수정)를](https://go.microsoft.com/fwlink/?linkid=852604)기반으로 하는 키워드 사전의 용어입니다. 이 유형은 설명이 아닌 보험 코드만 됩니다.

## <a name="international-classification-of-diseases-icd-9-cm"></a>국제적인 병 분류(ICD-9-CM)

### <a name="format"></a>형식

사전

### <a name="pattern"></a>패턴

키워드

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 검색된 Dictionary_icd_9_updated 발견됩니다.
- 검색된 Dictionary_icd_9_codes 발견됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 검색된 Dictionary_icd_9_updated 발견됩니다.

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

[ICD-9-CM(International Classification of Diseases,N9th Revision, ICD-9-CM)을](https://go.microsoft.com/fwlink/?linkid=852605)기반으로 하는 Dictionary_icd_9_updated 키워드 사전의 용어입니다. 이 유형은 보험 코드가 아니라 용어만 됩니다.

ICD-Dictionary_icd_9_codes 국제질병 [분류, 9번째 수정, ICD-9-CM(예방 수정)을](https://go.microsoft.com/fwlink/?linkid=852605)기반으로 하는 키워드 사전의 용어입니다. 이 유형은 설명이 아닌 보험 코드만 됩니다.

## <a name="ip-address"></a>IP 주소

### <a name="format"></a>형식

#### <a name="ipv4"></a>IPv4:
IPv4 주소의 서식 있는(기간) 및 서식 없는 버전(기간 없음)을 계정으로 표시하는 복잡한 패턴

#### <a name="ipv6"></a>IPv6:
서식이 있는 IPv6 번호(콜론 포함)를 계정을 표시하는 복잡한 패턴

### <a name="pattern"></a>패턴

### <a name="checksum"></a>체크섬

아니요

### <a name="definition"></a>정의

IPv6의 경우 DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- Regex_ipv6_address 정규식이 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_ipaddress의 키워드가 발견되지 않았습니다.

IPv4의 경우 DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- Regex_ipv4_address 정규식이 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_ipaddress의 키워드가 발견되었습니다.

IPv6의 경우 DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
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

- IP(이 키워드는 대소문자 구분)
- ip address
- ip addresses
- internet protocol
- IP-כתובת ה


## <a name="ip-address-v4"></a>IP 주소 v4

### <a name="format"></a>형식

IPv4 주소의 서식 있는(기간) 및 서식 없는 버전(기간 없음)을 계정으로 표시하는 복잡한 패턴

### <a name="pattern"></a>패턴


### <a name="checksum"></a>체크섬

아니요

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- `Regex_ipv4_address`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 시작 `Keyword_ipaddress` 키워드가 발견됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- `Regex_ipv4_address`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.


```xml
      <!-- IP Address v4--> 
      <Entity id="a7dd5e5f-e7f9-4626-a2c6-86a8cb6830d2" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_ipv4_address" />
          <Match idRef="Keyword_ipaddress" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ipv4_address" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_ipaddress"></a>Keyword_ipaddress

- IP(대소문자 구분)
- ip address
- ip addresses
- internet protocol
- IP-כתובת ה


## <a name="ip-address-v6"></a>IP 주소 v6

### <a name="format"></a>형식

서식이 있는 IPv6 번호(콜론 포함)를 계정을 표시하는 복잡한 패턴

### <a name="pattern"></a>패턴


### <a name="checksum"></a>체크섬

아니요

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- `Regex_ipv6_address`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 시작 `Keyword_ipaddress` 키워드가 발견됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- `Regex_ipv6_address`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.


```xml
      <!-- IP Address v6-->
      <Entity id="3f691089-7413-4926-ab3b-3c5ea8a1c17e" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_ipv6_address" />
          <Match idRef="Keyword_ipaddress" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ipv6_address" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_ipaddress"></a>Keyword_ipaddress

- IP(대소문자 구분)
- ip address
- ip addresses
- internet protocol
- IP-כתובת ה


## <a name="ireland-drivers-license-number"></a>아일랜드 운전 면허 번호

### <a name="format"></a>형식

6자리 숫자와 문자 4자

### <a name="pattern"></a>패턴

6자리 숫자와 4자리 문자:

- 6자리 숫자
- 4개의 문자(대소문자 구분 안 )

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.

- `Regex_ireland_eu_driver's_license_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_driver's_license_number` `Keywords_ireland_eu_driver's_license_number` 찾거나 찾은 경우

```xml
      <!-- Ireland Driver's License Number -->
      <Entity id="e01bccd9-eb4d-414f-ace1-e9b6a4c4a2ca" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_ireland_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv 라이선스
- driv 라이선스
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl 번호


#### <a name="keywords_ireland_eu_drivers_license_number"></a>Keywords_ireland_eu_driver s_license_number

- ceadúnas tiomána
- ceadúnais tiomána

## <a name="ireland-passport-number"></a>아일랜드 여권 번호

### <a name="format"></a>형식

공백이나 공백이 없는 7자리 숫자 2개

### <a name="pattern"></a>패턴

2개의 문자 또는 숫자와 7자리 숫자:

- 2자리 숫자 또는 문자(대소문자 구분 안 )
- 7자리 숫자

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- `Regex_ireland_eu_passport_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_passport_number` `Keywords_ireland_eu_passport_number` 찾거나 찾은 경우
- `Regex_ireland_eu_passport_date`정규식은 DD MMM/MMM YYYY(예제 - 01 BEA/MAY 1988) 형식의 날짜 또는 키워드가 `Keywords_eu_passport_date` 발견되었습니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- `Regex_ireland_eu_passport_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_passport_number` `Keywords_ireland_eu_passport_number` 찾거나 찾은 경우

```xml
      <!-- Ireland Passport Number -->
      <Entity id="a2130f27-9ee2-4103-84f9-a6b1ee7d0cbf" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_ireland_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_ireland_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_ireland_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_ireland_eu_passport_number"></a>Keywords_ireland_eu_passport_number

- passeport numero
- uimhreacha pasanna
- uimhir pas
- uimhir phas
- uimhreacha pas
- uimhir cárta
- uimhir chárta

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 문제의 날짜
- 만료 날짜


## <a name="ireland-personal-public-service-pps-number"></a>아일랜드 PPS(개인 공용 서비스) 번호

### <a name="format"></a>형식

이전 형식(2012년 12월 31일까지):
- 7자리 숫자와 1-2자리 문자

새 형식(2013년 1월 1일 이후):
- 7자리 숫자와 문자 2자

### <a name="pattern"></a>패턴

이전 형식(2012년 12월 31일까지):
- 7자리 숫자
- 1-2개 문자(대소문자 구분 안 )

새 형식(2013년 1월 1일 이후):
- 7자리 숫자
- 알파벳 검사 숫자인 문자(대소문자 구분 안 )입니다.
- A-I 범위의 선택적 문자 또는 "W"입니다.

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이 Func_ireland_pps 일치하는 콘텐츠를 검색합니다.
- 검색된 Keywords_ireland_eu_national_id_card 발견됩니다.
- 체크섬이 통과됩니다.

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있다는 신뢰도는 낮습니다.
- 이 Func_ireland_pps 일치하는 콘텐츠를 검색합니다.
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

- 클라이언트 ID 서비스
- identification number
- 개인 ID 번호
- 개인 공용 서비스 번호
- 개인 서비스 아니요
- phearsanta seirbhíse poiblí
- pps no
- pps 번호
- pps num
- pps 서비스 아니요
- ppsn
- ppsno #
- ppsno
- psp
- public service no
- publicserviceno #
- publicserviceno
- 수익 및 사회 보험 번호
- rsi no
- rsi 번호
- rsin
- seirbhís aitheantais 클라이언트
- uimh
- uimhir aitheantais chánach
- uimhir aitheantais phearsanta
- uimhir phearsanta seirbhíse poiblí
- tax id
- tax identification no
- tax identification number
- tax no #
- tax no
- tax number
- tax registration number
- 에 대한 나타 #
- 일자 #
- 일자 수 #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #


## <a name="israel-bank-account-number"></a>이스라엘 은행 계좌 번호

### <a name="format"></a>형식

13자리 숫자

### <a name="pattern"></a>패턴

서식 있는 형식:
- 2자리 숫자
- 대시
- 3자리 숫자
- 대시
- 8자리 숫자

비형성:
- 13자리 연속 숫자

### <a name="checksum"></a>체크섬

아니요

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
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

## <a name="israel-national-identification-number"></a>이스라엘 국가 ID 번호

### <a name="format"></a>형식

9자리 숫자

### <a name="pattern"></a>패턴

9자리 연속 숫자

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
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

-   מספר זהות
-   מספר זיה וי
-   מספר זיהוי ישר אלי      
-   זהותישר אלית
-   هو ية اسرائيل ية عدد
-   هوية إسرائ يلية
-   رقم الهوية
-   عدد هوية فريدة من نوعها
-   idnumber #
-   id number
-   IDENTITY no        
-   identitynumber #
-   ID 번호
-   israeliidentitynumber       
-   personal id
-   고유 ID  


## <a name="italy-drivers-license-number"></a>이탈리아 운전 면허 번호

이 유형 엔터티는 EU 운전 면허 번호 중요한 정보 유형에 포함됩니다. 독립 실행형 중요한 정보 유형 엔터티로도 사용할 수 있습니다.

### <a name="format"></a>형식

10자리 문자 및 숫자 조합

### <a name="pattern"></a>패턴

10자리 문자와 숫자의 조합:
- 한 문자(대소문자 구분 안 )
- 문자 "A" 또는 "V"(대소문자를 구분하지 않습니다.)
- 7자리 숫자
- 한 문자(대소문자 구분 안 )

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- `Regex_italy_drivers_license_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를 `Keywords_eu_driver's_license_number` `Keyword_italy_drivers_license_number` 찾거나 찾은 경우

```xml
    <!-- Italy Driver's license Number -->
    <Entity id="97d6244f-9157-41bd-8e0c-9d669a5c4d71" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_italy_drivers_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keyword_italy_drivers_license_number" />
          </Any>
        </Pattern>
    </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv 라이선스
- driv 라이선스
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl 번호

#### <a name="keyword_italy_drivers_license_number"></a>Keyword_italy_drivers_license_number

- numero di patente
- patente di guida
- patente guida
- patenti di guida
- patenti guida


## <a name="italy-fiscal-code"></a>이탈리아 회계 코드
이 중요한 정보 유형은 다음에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거버넌스
- 레코드 관리
- Microsoft 클라우드 앱 보안

### <a name="format"></a>형식

지정된 패턴의 문자 및 숫자 조합 16자

### <a name="pattern"></a>패턴

문자와 숫자의 16자 조합:
- 가족 이름의 처음 세 자석에 해당하는 3개의 문자
- 이름의 첫 번째, 세 번째 및 네 번째 자석에 해당하는 세 글자
- 생년월일의 마지막 숫자에 해당하는 두 자리 숫자
- 생년월일 문자에 해당하는 한 문자- 문자는 사전순으로 사용되지만 A에서 E, H, L, M, P, R에서 T까지의 문자만 사용됩니다(따라서 1월은 A, 10월은 R임).
- 성별을 차별화하기 위해 생년월일에 해당하는 두 자리 숫자, 여성의 생년월일에 40자리 추가
- 사람이 태어나는 지역 번호에 해당하는 4자리 숫자(국가 전체 코드가 외국 국가에 사용)
- 패리티 숫자 1개

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이  `Func_italy_eu_national_id_card` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 시작  `Keywords_italy_eu_national_id_card` 키워드가 발견됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 이  `Func_italy_eu_national_id_card` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.

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
- codice 회계
- codice id personale
- codice personale
- 회계 코드
- numero certificato personale
- numero di identificazione 회계
- numero id personale
- numero personale
- 개인 인증서 번호
- 개인 코드
- 개인 ID 코드
- 개인 ID 번호
- personalcodeno #
- tax code
- tax id
- tax identification no
- tax identification number
- tax identity number
- tax no #
- tax no
- tax number
- tax registration number
- 에 대한 나타 #
- 일자 #
- 일자 수 #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #


## <a name="italy-passport-number"></a>이탈리아 여권 번호

### <a name="format"></a>형식

공백이나 공백이 없는 7자리 숫자와 문자 2자 또는 숫자

### <a name="pattern"></a>패턴

2개의 문자 또는 숫자와 7자리 숫자:

- 2자리 숫자 또는 문자(대소문자 구분 안 )
- 7자리 숫자

### <a name="checksum"></a>체크섬

해당 없음

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- `Regex_italy_eu_passport_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_passport_number` `Keywords_italy_eu_passport_number` 찾거나 찾은 경우
- `Regex_italy_eu_passport_date`정규식은 DD MMM/MMM YYYY(예제 - 01 GEN/JAN 1988) 형식의 날짜 또는 키워드가 `Keywords_eu_passport_date` 발견되었습니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- `Regex_italy_eu_passport_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_passport_number` `Keywords_italy_eu_passport_number` 찾거나 찾은 경우

```xml
      <!-- Italy Passport Number -->
      <Entity id="39811019-4750-445f-b26d-4c0e6c431544" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_italy_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_italy_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_italy_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_italy_eu_passport_number"></a>Keywords_italy_eu_passport_number

- italiana passaporto
- passaporto 이탈리아어
- passaporto numero
- numéro passeport
- numero di passaporto
- numeri del passaporto
- passeport italien

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 문제의 날짜
- 만료 날짜


## <a name="italy-value-added-tax-number"></a>이탈리아 부가가치세 번호
이 중요한 정보 유형은 다음에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거버넌스
- 레코드 관리
- Microsoft 클라우드 앱 보안

### <a name="format"></a>형식

선택적 소수점 문자가 있는 13자 영문자 패턴

### <a name="pattern"></a>패턴

선택적 delimiters가 있는 13자 영문자 패턴:

- I 또는 i
- T 또는 t
- 선택적 공백, 점, 하이픈 또는 콤보
- 11자리 숫자

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이 Func_italy_value_added_tax_number 일치하는 콘텐츠를 검색합니다.
- 검색된 Keywords_italy_value_added_tax_number 발견됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 이 Func_italy_value_added_tax_number 일치하는 콘텐츠를 검색합니다.

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

- vat number
- vat no
- vat #
- iva
- iva #


## <a name="japan-bank-account-number"></a>일본 은행 계좌 번호

### <a name="format"></a>형식

7 또는 8자리 숫자

### <a name="pattern"></a>패턴

bank account number:
- 7 또는 8자리 숫자
- bank account branch code:
- 4자리 숫자
- 공백 또는 대시(선택 사항)
- 3자리 숫자

체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- Func_jp_bank_account 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_jp_bank_account의 키워드가 발견되었습니다.
- 다음 중 하나가 충족됩니다.
- Func_jp_bank_account_branch_code 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_jp_bank_branch_code의 키워드가 발견되었습니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
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
- 口座番号
- 銀行口座
- 銀行口座番号
- 総合口座
- 普通預金口座
- 普通口座
- 当座預金口座
- 当座口座
- 預金口座
- 振替口座
- 銀行
- バンク

#### <a name="keyword_jp_bank_branch_code"></a>Keyword_jp_bank_branch_code

- 支店番号
- 支店コード
- 店番号

## <a name="japan-drivers-license-number"></a>일본 운전 면허 번호

### <a name="format"></a>형식

12자리 숫자

### <a name="pattern"></a>패턴

12자리 연속 숫자

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
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

- driverlicense
- driverslicense
- driver'slicense
- driverslicenses
- driver'slicenses
- driverlicenses
- dl #
- dls #
- lic #
- lics #
- 運転免許証
- 運転免許
- 免許証
- 免許
- 運転免許証番号
- 運転免許番号
- 免許証番号
- 免許番号
- 運転免許証ナンバー
- 運転免許ナンバー
- 免許証ナンバー
- 運転免許証no
- 運転免許no
- 免許証no
- 免許no
- 運転経歴証明書番号
- 運転経歴証明書
- 運転免許証No.
- 運転免許No.
- 免許証No.
- 免許No.
- 運転免許証 #
- 運転免許 #
- 免許証 #
- 免許 #


## <a name="japan-my-number---corporate"></a>일본 내 번호 - 회사

이 중요한 정보 유형은 다음에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거버넌스
- 레코드 관리
- Microsoft 클라우드 앱 보안

### <a name="format"></a>형식

13자리 숫자

### <a name="pattern"></a>패턴

13자리 숫자:

- 1자리에서 9자리까지의 1자리 숫자
- 12자리 숫자

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이 Func_japanese_my_number_corporate 패턴과 일치하는 콘텐츠를 검색합니다.
- 검색된 Keywords_japanese_my_number_corporate 발견됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 이 Func_japanese_my_number_corporate 패턴과 일치하는 콘텐츠를 검색합니다.

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


## <a name="japan-my-number---personal"></a>일본 내 번호 - 개인

이 중요한 정보 유형은 다음에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거버넌스
- 레코드 관리
- Microsoft 클라우드 앱 보안

### <a name="format"></a>형식

12자리 숫자

### <a name="pattern"></a>패턴

12자리 숫자:

- 4자리 숫자
- 선택적 공백, 점 또는 하이픈
- 4자리 숫자
- 선택적 공백, 점 또는 하이픈
- 4자리 숫자

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이 Func_japanese_my_number_personal 패턴과 일치하는 콘텐츠를 검색합니다.
- 검색된 Keywords_japanese_my_number_personal 발견됩니다.

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있다는 신뢰도는 낮습니다.
- 이 Func_japanese_my_number_personal 패턴과 일치하는 콘텐츠를 검색합니다.

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

- my number
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

### <a name="format"></a>형식

2개의 문자와 7자리 숫자

### <a name="pattern"></a>패턴

2개의 문자(대소문자 구분 안 ), 7자리 숫자

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
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

- Passport
- Passport Number
- Passport No.
- Passport #
- パスポート
- パスポート番号
- パスポートナンバー
- パスポート＃
- パスポート #
- ストトトNo.
- 旅券番号
- 旅券番号＃
- 旅券番号♯
- 旅券ナンバー


## <a name="japan-residence-card-number"></a>일본 거주 카드 번호

### <a name="format"></a>형식

문자 및 숫자 12개

### <a name="pattern"></a>패턴

12개 문자 및 숫자:
- 2개 문자(대소문자 구분 안 )
- 8자리 숫자
- 2개 문자(대소문자 구분 안 )

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 정규식 Regex_jp_residence_card_number 일치하는 콘텐츠를 검색합니다.
- 검색된 Keyword_jp_residence_card_number 발견됩니다.

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

- 거주 카드 번호
- 거주 카드 아니요
- 거주 카드 #
- 在留カード番号
- 在留カード
- 在留番号

## <a name="japan-resident-registration-number"></a>일본 거주 등록 번호

### <a name="format"></a>형식

11자리 숫자

### <a name="pattern"></a>패턴

11자리 연속 숫자

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
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
- Residents Basic Registry Number
- Resident Registration No.
- Resident Register No.
- Residents Basic Registry No.
- Basic Resident Register No.
- 外国人登録証明書番号
- 証明書番号
- 登録番号
- 外国人登録証


## <a name="japan-social-insurance-number-sin"></a>일본 SIN(사회 보험 번호)

### <a name="format"></a>형식

7-12자리 숫자

### <a name="pattern"></a>패턴

7-12자리 숫자:
- 4자리 숫자
- 하이픈(선택 사항)
- 6자리 숫자 OR
- 7-12자리 연속 숫자

### <a name="checksum"></a>체크섬

아니요

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- Func_jp_sin 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_jp_sin의 키워드가 발견되었습니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
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
- 健康保険被保険者番号
- 健保番号
- 基礎年金番号
- 雇用保険被保険者番号
- 雇用保険番号
- 保険証番号
- 社会保険番号
- 会保険No.
- 社会保険
- 介護保険
- 介護保険被保険者番号
- 健康保険被保険者整理番号
- 雇用保険被保険者整理番号
- 厚生年金
- 厚生年金被保険者整理番号


## <a name="latvia-drivers-license-number"></a>라트비아 운전 면허 번호

### <a name="format"></a>형식

3개의 문자와 6자리 숫자

### <a name="pattern"></a>패턴

3개의 문자와 6자리 숫자:

- 3개의 문자(대소문자 구분 안 )
- 6자리 숫자

### <a name="checksum"></a>체크섬

아니요

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- `Regex_latvia_eu_driver's_license_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_driver's_license_number` `Keywords_latvia_eu_driver's_license_number` 찾거나 찾은 경우

```xml
      <!-- Latvia Driver's License Number -->
      <Entity id="ec996de0-30f2-46b1-b192-4d2ff8805fa7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_latvia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv 라이선스
- driv 라이선스
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl 번호


#### <a name="keywords_latvia_eu_drivers_license_number"></a>Keywords_latvia_eu_driver s_license_number

- autovadītāja apliecība
- autovadītāja apliecības
- vadītāja apliecība

## <a name="latvia-personal-code"></a>라트비아 개인 코드

### <a name="format"></a>형식

11자리 숫자 및 하이픈(선택 사항)

### <a name="pattern"></a>패턴

이전 형식

11자리 숫자와 하이픈:

- 생년월일(DDMMYY)에 해당하는 6자리 숫자
- 하이픈
- 생년월일(19번째 19번째 10년의 경우 "1", 21세기의 경우 "2")에 해당하는 1자리 숫자
- 4자리 숫자( 임의로 생성)

새 형식

11자리 숫자

- 두 자리 숫자 "32"
- 9자리 숫자

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 함수 또는  `Func_latvia_eu_national_id_card` regex가 `Regex_latvia_eu_national_id_card_new_format` 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 시작  `Keywords_latvia_eu_national_id_card` 키워드가 발견됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 함수 또는  `Func_latvia_eu_national_id_card` regex가 `Regex_latvia_eu_national_id_card_new_format` 해당 패턴과 일치하는 콘텐츠를 검색합니다.

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
- alvas nē
- birth number
- citizen number
- 매수
- electronic census number
- electronic number
- 회계 코드
- healthcare 사용자 번호
- id #
- id-code
- identification number
- identifikācijas numurs
- id-number
- 개별 번호
- latvija alva
- nacionālais id
- national id
- national identifying number
- national identity number
- national insurance number
- national register number
- nodokļa numurs
- nodokļu ID
- nodokļu identifikācija numurs
- 개인 인증서 번호
- 개인 코드
- 개인 ID 코드
- 개인 ID 번호
- 개인 식별 코드
- 개인 식별자
- 개인 ID 번호
- personal number
- 개인 숫자 코드
- personalcodeno #
- personas kods
- population identification code
- 공용 서비스 번호
- registration number
- revenue number
- social insurance number
- social security number
- 주 세금 코드
- tax file number
- tax id
- tax identification no
- tax identification number
- tax no #
- tax no
- tax number
- 에 대한 나타 #
- 일자 #
- 일자 수 #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #
- 투표자 번호

## <a name="latvia-passport-number"></a>라트비아 여권 번호

### <a name="format"></a>형식

공백이나 공백이 없는 7자리 숫자와 문자 2자 또는 숫자

### <a name="pattern"></a>패턴

2개의 문자 또는 숫자와 7자리 숫자:

- 2자리 숫자 또는 문자(대소문자 구분 안 )
- 7자리 숫자

### <a name="checksum"></a>체크섬

아니요

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- `Regex_latvia_eu_passport_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_passport_number` `Keywords_latvia_eu_passport_number` 찾거나 찾은 경우
- `Regex_eu_passport_date1`정규식이 DD.MM.YYYY 형식의 날짜를 찾거나 키워드를 `Keywords_eu_passport_date` 찾은 경우

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- `Regex_latvia_eu_passport_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_passport_number` `Keywords_latvia_eu_passport_number` 찾거나 찾은 경우

```xml
      <!-- Latvia Passport Number -->
      <Entity id="23ae25ec-cc28-421b-b77a-3054eadf1ede" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_latvia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_latvia_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_latvia_eu_passport_number"></a>Keywords_latvia_eu_passport_number

- pase numurs
- pase numur
- pases numuri
- pases nr
- passeport no
- n° du Passeport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 문제의 날짜
- 만료 날짜


## <a name="lithuania-drivers-license-number"></a>리투아니아 운전 면허 번호

### <a name="format"></a>형식

공백 및 디지타이터가 없는 8자리 숫자

### <a name="pattern"></a>패턴

8자리 숫자

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- `Regex_lithuania_eu_driver's_license_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_driver's_license_number` `Keywords_lithuania_eu_driver's_license_number` 찾거나 찾은 경우

```xml
      <!-- Lithuania Driver's License Number -->
      <Entity id="86f7628b-e0f4-4dc3-9fbc-e4300e4c7d78" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv 라이선스
- driv 라이선스
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl 번호


#### <a name="keywords_lithuania_eu_drivers_license_number"></a>Keywords_lithuania_eu_driver s_license_number

- vairuotojo pažymėjimas
- vairuotojo pažymėjimo 숫자
- vairuotojo pažymėjimo numeriai

## <a name="lithuania-personal-code"></a>리투아니아 개인 코드
이 중요한 정보 유형은 다음에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거버넌스
- 레코드 관리
- Microsoft 클라우드 앱 보안

### <a name="format"></a>형식

공백 및 디지타이터가 없는 11자리 숫자

### <a name="pattern"></a>패턴

공백 및 디지타이터가 없는 11자리 숫자:

- 생년월일과 성별 및 세기에 해당하는 1자리 숫자(1-6)입니다.
- 생년월일(YYMMDD)에 해당하는 6자리 숫자
- 생년월일 일련 번호에 해당하는 세 자리 숫자
- 검사 숫자 1개

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이  `Func_lithuania_eu_tax_file_number` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 시작  `Keywords_lithuania_eu_tax_file_number` 키워드가 발견됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 이  `Func_lithuania_eu_tax_file_number` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.

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

- asmeninis skaitmeninis kodas
- asmens kodas
- citizen service number
- mokesčių ID
- mokesčių identifikavimas numeris
- mokesčių identifikavimo numeris
- mokesčių 숫자
- national identification number
- 개인 코드
- 개인 숫자 코드
- piliečio paslaugos numeris
- tax id
- tax identification no
- tax identification number
- tax no #
- tax no
- tax number
- tax registration number
- 에 대한 나타 #
- 일자 #
- 일자 수 #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #
- unikalus identifikavimo kodas
- unikalus identifikavimo numeris
- 고유 ID 번호
- 고유 ID 번호
- uniqueidentityno #

## <a name="lithuania-passport-number"></a>리투아니아 여권 번호

### <a name="format"></a>형식

공백이나 공백이 없는 8자리 숫자 또는 문자

### <a name="pattern"></a>패턴

8자리 숫자 또는 문자(대소문자 구분 안 )

### <a name="checksum"></a>체크섬

해당 없음

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- `Regex_lithuania_eu_passport_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_passport_number` `Keywords_lithuania_eu_passport_number` 찾거나 찾은 경우
- 정규식이 DD MM YYYY 형식의 날짜를 찾거나 `Regex_eu_passport_date3` 키워드를 `Keywords_eu_passport_date` 찾은 경우

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- `Regex_lithuania_eu_passport_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_passport_number` `Keywords_lithuania_eu_passport_number` 찾거나 찾은 경우

```xml
      <!-- Lithuania Passport Number -->
      <Entity id="1b79900f-047b-4c3f-846f-7d73b5534bce" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_lithuania_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date3" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_lithuania_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_lithuania_eu_passport_number"></a>Keywords_lithuania_eu_passport_number

- paso numeris
- paso numeriai
- paso nr

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 문제의 날짜
- 만료 날짜


## <a name="luxemburg-drivers-license-number"></a>룩세르버그 운전 면허 번호

### <a name="format"></a>형식

공백 및 디지타이터가 없는 6자리 숫자

### <a name="pattern"></a>패턴

6자리 숫자

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- `Regex_luxemburg_eu_driver's_license_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_driver's_license_number` `Keywords_luxemburg_eu_driver's_license_number` 찾거나 찾은 경우

```xml
      <!-- Luxemburg Driver's License Number -->
      <Entity id="89daf717-1544-4860-9a2e-fc9166dd8852" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv 라이선스
- driv 라이선스
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl 번호


#### <a name="keywords_luxemburg_eu_drivers_license_number"></a>Keywords_luxemburg_eu_driver s_license_number

- fahrerlaubnis
- Führerschäin

## <a name="luxemburg-national-identification-number-natural-persons"></a>룩룩부르크 국가 ID 번호(자연인)
이 중요한 정보 유형은 다음에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거버넌스
- 레코드 관리
- Microsoft 클라우드 앱 보안

### <a name="format"></a>형식

공백이나 디지타이터가 없는 13자리 숫자

### <a name="pattern"></a>패턴

13자리 숫자:

- 11자리 숫자
- 검사 숫자 2개

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이  `Func_luxemburg_eu_tax_file_number` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 시작  `Keywords_luxemburg_eu_national_id_card` 키워드가 발견됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 이  `Func_luxemburg_eu_tax_file_number` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.


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
- 유휴 직원
- idpersonnelle #
- idpersonnelle
- 개별 코드
- 개별 ID
- 개별 식별
- 개별 ID
- numéro d'identification personnel
- personal id
- personal identification
- 개인 ID
- personalidno #
- personalidnumber #
- persönliche identifikationsnummer
- 고유 ID
- 고유 ID
- uniqueidkey #

## <a name="luxemburg-passport-number"></a>룩세르버그 여권 번호

### <a name="format"></a>형식

공백이나 공백이 없는 8자리 숫자 또는 문자

### <a name="pattern"></a>패턴

8자리 숫자 또는 문자(대소문자 구분 안 )

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- `Regex_luxemburg_eu_passport_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_passport_number` `Keywords_luxemburg_eu_passport_number` 찾거나 찾은 경우
- 정규식이 DD MM YYYY 형식의 날짜를 찾거나 `Regex_eu_passport_date3` 키워드를 `Keywords_eu_passport_date` 찾은 경우

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- `Regex_luxemburg_eu_passport_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_passport_number` `Keywords_luxemburg_eu_passport_number` 찾거나 찾은 경우

```xml
      <!-- Luxemburg Passport Number -->
      <Entity id="81d5c027-bed9-4421-91a0-3b2e55b3eb85" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_luxemburg_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_luxemburg_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date3" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_luxemburg_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_luxemburg_eu_passport_number"></a>Keywords_luxemburg_eu_passport_number
- ausweisnummer
- luxembourg pass
- luxembourg passeport
- luxembourg passport
- de passeport 없음
- no-reisepass
- nr-reisepass
- numéro de passeport
- pass net
- nr 전달
- passnummer
- passeport nombre
- reisepässe
- reisepass-nr
- reisepassnummer

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 문제의 날짜
- 만료 날짜


## <a name="luxemburg-national-identification-number-non-natural-persons"></a>룩룩부르크 국가 ID 번호(자연인이 아닌 사람)

### <a name="format"></a>형식

11자리 숫자

### <a name="pattern"></a>패턴

11자리 숫자

- 2자리 숫자
- 선택적 공백
- 3자리 숫자
- 선택적 공백
- 3자리 숫자
- 선택적 공백
- 2자리 숫자
- 검사 숫자 1개

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이  `Func_luxemburg_eu_tax_file_number_non_natural` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 시작  `Keywords_luxemburg_eu_tax_file_number` 키워드가 발견됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 이  `Func_luxemburg_eu_tax_file_number_non_natural` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.

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

- carte de sécurité sociale
- étain non
- étain #
- identifiant d'impôt
- luxembourg tax identifikatiounsnummer
- numéro d'étain
- numéro d'identification fiscal luxembourgeois
- numéro d'identification 회계
- social security
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
- tax identification no
- tax identification number
- tax no #
- tax no
- tax number
- tax registration number
- 에 대한 나타 #
- 일자 #
- 일자 수 #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #
- zinn #
- zinn
- zinnzahl


## <a name="malaysia-identification-card-number"></a>말레이시아 ID 카드 번호

### <a name="format"></a>형식

선택적으로 하이픈을 포함하는 12자리 숫자

### <a name="pattern"></a>패턴

12자리 숫자:
- 생년월일인 YYMMDD 형식의 6자리 숫자
- 대시(선택 사항)
- 2문자 생년월일 코드
- 대시(선택 사항)
- 3개의 임의 숫자
- 1자리 성별 코드

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 정규식 Regex_malaysia_id_card_number 일치하는 콘텐츠를 검색합니다.
- 검색된 Keyword_malaysia_id_card_number 발견됩니다.

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
- i/c no
- ic
- ic no
- id card
- identification Card
- identity card
- k/p
- k/p no
- kad akuan diri
- kad aplikasi 디지털
- kad pengenalan malaysia
- kp
- kp no
- mykad
- mykas
- mykid
- mypr
- mytentera
- 말레이시아 ID 카드
- malaysian identity card
- nric
- 개인 식별 카드

## <a name="malta-drivers-license-number"></a>몰타 운전 면허 번호

### <a name="format"></a>형식

지정된 패턴의 2자 및 6자리 숫자 조합

### <a name="pattern"></a>패턴

2개의 문자와 6자리 숫자의 조합:

- 2자(숫자 또는 문자, 대소문자 구분 안 )
- 공백(선택 사항)
- 3자리 숫자
- 공백(선택 사항)
- 3자리 숫자

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- `Regex_malta_eu_driver's_license_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_driver's_license_number` `Keywords_malta_eu_driver's_license_number` 찾거나 찾은 경우

```xml
      <!-- Malta Driver's License Number -->
      <Entity id="a3bdaa4a-8371-4735-8fa5-56ee0fb4afc4" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_malta_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv 라이선스
- driv 라이선스
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl 번호


#### <a name="keywords_malta_eu_drivers_license_number"></a>Keywords_malta_eu_driver s_license_number

- liċenzja -tas-의 자식qan
- liċenzji-tas-pwieq


## <a name="malta-identity-card-number"></a>몰타 ID 카드 번호
이 중요한 정보 유형은 다음에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거버넌스
- 레코드 관리
- Microsoft 클라우드 앱 보안

### <a name="format"></a>형식

7자리 숫자와 한 문자

### <a name="pattern"></a>패턴

7자리 숫자와 한 글자:

- 7자리 숫자
- "M, G, A, P, L, H, B, Z"(대소문자 미정)

### <a name="checksum"></a>체크섬

해당 없음

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- `Regex_malta_eu_national_id_card`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 시작  `Keywords_malta_eu_national_id_card` 키워드가 발견됩니다.

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있다는 신뢰도는 낮습니다.
- `Regex_malta_eu_national_id_card`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.

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

- citizen service number
- id tat-taxxa
- identifika numru tal-biljett
- kodiċi 개인 정보
- numru ta 'identifikazzjoni personali
- numru ta 'identifikazzjoni tat-taxxa
- numru ta 'identifikazzjoni uniku
- numru ta' identità uniku
- numru tas-servizz taċ-ċittadin
- numru tat-taxxa
- 개인 숫자 코드
- 고유 ID 번호
- 고유 ID 번호
- uniqueidentityno #


## <a name="malta-passport-number"></a>몰타 여권 번호

### <a name="format"></a>형식

공백이나 디지타이터가 없는 7자리 숫자

### <a name="pattern"></a>패턴

7자리 숫자

### <a name="checksum"></a>체크섬

아니요

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- `Regex_malta_eu_passport_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_passport_number` `Keywords_malta_eu_passport_number` 찾거나 찾은 경우
- 키워드를 `Keywords_eu_passport_date` 찾은 경우

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- `Regex_malta_eu_passport_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_passport_number` `Keywords_malta_eu_passport_number` 찾거나 찾은 경우

```xml
      <!-- Malta Passport Number -->
      <Entity id="b2b21198-48f9-4d13-b2a5-03969bff0fb8" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_malta_eu_passport_number" />
          </Any>
          <Match idRef="Keywords_eu_passport_date" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_malta_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_malta_eu_passport_number"></a>Keywords_malta_eu_passport_number

- numru tal-passaport
- numri tal-passaport
- Nru tal-passaport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 문제의 날짜
- 만료 날짜


## <a name="malta-tax-identification-number"></a>몰타 세금 식별 번호

### <a name="format"></a>형식

몰타어 국가:
- 지정된 패턴의 7자리 숫자와 한 문자

몰타어가 아닌 국가 및 몰타 엔터티:
- 9자리 숫자

### <a name="pattern"></a>패턴

몰타 국가: 7자리 숫자 및 문자 1자

- 7자리 숫자
- 한 문자(대소문자 구분 안 )

몰타어가 아닌 국가 및 몰타 엔터티: 9자리 숫자

- 9자리 숫자

### <a name="checksum"></a>체크섬

해당 사항 없음

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- regex  `Regex_malta_eu_tax_file_number`  또는 `Regex_malta_eu_tax_file_number_non_maltese_national` 패턴과 일치하는 콘텐츠를 찾습니다.
- 시작  `Keywords_malta_eu_tax_file_number` 키워드가 발견됩니다.

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있다는 신뢰도는 낮습니다.
- regex  `Regex_malta_eu_tax_file_number` 또는 `Regex_malta_eu_tax_file_number_non_maltese_national` 패턴과 일치하는 콘텐츠를 찾습니다.

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

- citizen service number
- id tat-taxxa
- identifika numru tal-biljett
- kodiċi 개인 정보
- numru ta 'identifikazzjoni personali
- numru ta 'identifikazzjoni tat-taxxa
- numru ta 'identifikazzjoni uniku
- numru ta' identità uniku
- numru tas-servizz taċ-ċittadin
- numru tat-taxxa
- 개인 숫자 코드
- tax id
- tax identification no
- tax identification number
- tax no #
- tax no
- tax number
- tax registration number
- 에 대한 나타 #
- 일자 #
- 일자 수 #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #
- 고유 ID 번호
- 고유 ID 번호
- uniqueidentityno #


## <a name="medicare-beneficiary-identifier-mbi-card"></a>Medicare Beneficiary Identifier(MBI) 카드

### <a name="format"></a>형식

영문자 11자 패턴

### <a name="pattern"></a>패턴

- 1에서 9 사이의 1자리 숫자
- S, L, O, I, B, Z를 제외한 한 문자
- S, L, O, I, B, Z를 제외한 한 자리 숫자 또는 문자
- 1자리 숫자
- 선택적 하이픈
- S, L, O, I, B, Z를 제외한 한 문자
- S, L, O, I, B, Z를 제외한 한 자리 숫자 또는 문자
- 1자리 숫자
- 선택적 하이픈
- S, L, O, I, B, Z를 제외한 두 글자
- 2자리 숫자

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- `Regex_mbi_card`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 시작  `Keyword_mbi_card` 키워드가 발견됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- `Regex_mbi_card`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.

```xml
    <!-- Medicare Beneficiary Identifier (MBI) card -->
      <Entity id="f753a286-f5cc-47e6-a592-4be25fd02591" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_mbi_card" />
          <Match idRef="Keyword_mbi_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_mbi_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_mbi_card"></a>Keyword_mbi_card

- mbi
- mbi #
- medicare beneficiary #
- medicare 수급자 식별자
- medicare beneficiary no
- medicare beneficiary number
- medicare beneficiary #


## <a name="mexico-unique-population-registry-code-curp"></a>멕시코 고유의 인구 레지스트리 코드(CURP)

### <a name="format"></a>형식

영문자 18자 패턴

### <a name="pattern"></a>패턴

- 4개의 문자(대소문자 미지정)
- 유효한 날짜를 나타내는 6자리 숫자
- 문자 - H/h 또는 M/m
- 유효한 멕시코 상태 코드를 나타내는 두 글자
- 3개의 문자
- 한 문자 또는 숫자
- 1자리 숫자

### <a name="checksum"></a>체크섬

아니요

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이  `Func_mexico_population_registry_code` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 시작  `Keyword_mexico_population_registry_code` 키워드가 발견됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 이  `Func_mexico_population_registry_code` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.

```xml
    <!-- Mexico Unique Population Registry Code (CURP) -->
      <Entity id="e905ad4d-5a74-406d-bf36-b1efca798af4" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_mexico_population_registry_code" />
          <Match idRef="Keyword_mexico_population_registry_code" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_mexico_population_registry_code" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_mexico_population_registry_code"></a>Keyword_mexico_population_registry_code

- Clave Única de Registro de Población
- Clave Unica de Registro de Poblacion
- 고유 인구 레지스트리 코드 
- 고유 인구 코드
- CURP
- 개인 ID
- 고유 ID
- personalid
- personalidnumber
- uniqueidkey
- uniqueidnumber
- clave única
- 클래브 유니카
- clave personal Identidad
- personal Identidad Clave
- ClaveÚnica
- claveunica
- clavepersonalIdentidad


## <a name="netherlands-citizens-service-bsn-number"></a>네덜란드 시민 서비스(BSN) 번호

### <a name="format"></a>형식

선택적 공백을 포함하는 8 또는 9자리 숫자

### <a name="pattern"></a>패턴

8-9자리 숫자:
- 3자리 숫자
- 공백(선택 사항)
- 3자리 숫자
- 공백(선택 사항)
- 2-3자리 숫자

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이 Func_netherlands_bsn 패턴과 일치하는 콘텐츠를 검색합니다.
- 검색된 Keyword_netherlands_bsn 발견됩니다.
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
- citizen service number
- person number
- personal number
- 개인 숫자 코드
- 개인 관련 번호
- persoonlijk nummer
- persoonlijke 숫자 코드
- persoonsgebonden
- persoonsnummer
- sociaal-fiscaal nummer
- social-fiscal number
- sofi
- sofinummer
- uniek identificatienummer
- uniek identiteitsnummer
- 고유 ID 번호
- 고유 ID 번호
- uniqueidentityno #

## <a name="netherlands-drivers-license-number"></a>네덜란드 운전 면허 번호

### <a name="format"></a>형식

공백 및 디지타이터가 없는 10자리 숫자

### <a name="pattern"></a>패턴

10자리 숫자

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- `Regex_netherlands_eu_driver's_license_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_driver's_license_number` `Keywords_netherlands_eu_driver's_license_number` 찾거나 찾은 경우

```xml
      <!-- Netherlands Driver's License Number -->
      <Entity id="6247fbea-ab80-4be5-8233-308b7c031401" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
            </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv 라이선스
- driv 라이선스
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl 번호


#### <a name="keywords_netherlands_eu_drivers_license_number"></a>Keywords_netherlands_eu_driver s_license_number

- permis de conduire
- rijbewijs
- rijbewijsnummer
- rijbewijzen
- rijbewijs nummer
- rijbewijsnummers


## <a name="netherlands-passport-number"></a>네덜란드 여권 번호

### <a name="format"></a>형식

공백이나 디지타이터가 없는 9개의 문자 또는 숫자

### <a name="pattern"></a>패턴

9개의 문자 또는 숫자

### <a name="checksum"></a>체크섬

해당 없음

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- `Regex_netherlands_eu_passport_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_passport_number` `Keywords_netherlands_eu_passport_number` 찾거나 찾은 경우
- `Regex_netherlands_eu_passport_date`정규식은 DD MMM/MMM YYYY 형식의 날짜를 검색합니다(예제 - 26 MAA/MAR 2012)

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- `Regex_netherlands_eu_passport_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_passport_number` `Keywords_netherlands_eu_passport_number` 찾거나 찾은 경우

```xml
      <!-- Netherlands Passport Number -->
      <Entity id="61786727-bafd-45f6-94d9-888d815e228e" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Regex_netherlands_eu_passport_date" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_netherlands_eu_passport_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_netherlands_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_netherlands_eu_passport_number"></a>Keywords_netherlands_eu_passport_number

- paspoort nummer
- paspoortnummers
- paspoortnummer
- paspoort nr

## <a name="netherlands-tax-identification-number"></a>네덜란드 세금 ID 번호
이 중요한 정보 유형은 다음에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거버넌스
- 레코드 관리
- Microsoft 클라우드 앱 보안

### <a name="format"></a>형식

공백이나 디지타이터가 없는 9자리 숫자

### <a name="pattern"></a>패턴

9자리 숫자

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이  `Func_netherlands_eu_tax_file_number` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 시작  `Keywords_netherlands_eu_tax_file_number` 키워드가 발견됩니다.

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있다는 신뢰도는 낮습니다.
- 이  `Func_netherlands_eu_tax_file_number` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.

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

- btw nummer
- hollânske 세금 식별
- hulandes impuesto id number
- hulandes impuesto identification
- identificatienummer belasting
- identificatienummer van belasting
- impuesto identification number
- impuesto number
- nederlands belasting id nummer
- nederlands belasting identificatie
- nederlands belasting identificatienummer
- nederlands belastingnummer
- nederlandse belasting identificatie
- 네덜란드 세금 식별
- netherland의 세금 식별
- 네덜란드 주석
- netherland's tin
- tax id
- tax identification no
- tax identification number
- tax identification tal
- tax no #
- tax no
- tax number
- tax registration number
- tax tal
- 에 대한 나타 #
- 일자 #
- 일자 수 #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #


## <a name="netherlands-value-added-tax-number"></a>네덜란드 부가가치세 번호
이 중요한 정보 유형은 다음에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거버넌스
- 레코드 관리
- Microsoft 클라우드 앱 보안

### <a name="format"></a>형식

영문자 14자 패턴

### <a name="pattern"></a>패턴

14자 영문 패턴:

- N 또는 n
- L 또는 l
- 선택적 공백, 점 또는 하이픈
- 9자리 숫자
- 선택적 공백, 점 또는 하이픈
- B 또는 b
- 2자리 숫자

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이 Func_netherlands_value_added_tax_number 패턴과 일치하는 콘텐츠를 검색합니다.
- 검색된 Keywords_netherlands_value_added_tax_number 발견됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 이 Func_netherlands_value_added_tax_number 패턴과 일치하는 콘텐츠를 검색합니다.

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

- vat number
- vat no
- vat #
- wearde tafoege tax getal
- btw nûmer
- btw-nummer


## <a name="new-zealand-bank-account-number"></a>뉴질랜드 은행 계좌 번호
이 중요한 정보 유형은 다음에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거버넌스
- 레코드 관리
- Microsoft 클라우드 앱 보안

### <a name="format"></a>형식

선택적 디지타이터가 있는 14자리에서 16자리 패턴으로

### <a name="pattern"></a>패턴

선택적 디지타이터가 있는 14자리에서 16자리 패턴으로:

- 2자리 숫자
- 선택적 하이픈 또는 공백
- 3-4자리 숫자
- 선택적 하이픈 또는 공백
- 7자리 숫자
- 선택적 하이픈 또는 공백
- 2-3자리 숫자
- 옵션 하이픈 또는 공백

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이 Func_new_zealand_bank_account_number 일치하는 콘텐츠를 검색합니다.
- 검색된 Keywords_new_zealand_bank_account_number 발견됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 이 Func_new_zealand_bank_account_number 일치하는 콘텐츠를 검색합니다.

```xml
      <!-- New Zealand Bank Account Number -->
      <Entity id="1a97fc2b-dd2f-48f1-bc4e-2ddf25813956" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_new_zealand_bank_account_number" />
          <Match idRef="Keywords_new_zFealand_bank_account_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_new_zealand_bank_account_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_new_zealand_bank_account_number"></a>Keyword_new_zealand_bank_account_number

- account number
- bank account
- bank_acct_id
- bank_acct_branch
- bank_acct_nbr


## <a name="new-zealand-drivers-license-number"></a>뉴질랜드 운전 면허 번호
이 중요한 정보 유형은 다음에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거버넌스
- 레코드 관리
- Microsoft 클라우드 앱 보안

### <a name="format"></a>형식

영문자 8자 패턴

### <a name="pattern"></a>패턴

영문자 8자 패턴

- 두 글자
- 6자리 숫자

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이 Func_newzealand_driver_license_number 일치하는 콘텐츠를 검색합니다.
- 검색된 Keywords_newzealand_driver_license_number 발견됩니다.

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있다는 신뢰도는 낮습니다.
- 이 Func_newzealand_driver_license_number 일치하는 콘텐츠를 검색합니다.

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
- driver lic
- driver licence
- driver licences
- driverslic
- driverslicence
- driverslicences
- drivers lic
- drivers lics
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's licence
- driver's licences
- driverlic #
- driverlics #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver licence #
- driver licences #
- driverslic #
- driverslics #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's licence #
- driver's licences #
- international driving permit
- international driving permits
- nz 자동차 연결
- 뉴질랜드 자동차 협회


## <a name="new-zealand-inland-revenue-number"></a>뉴질랜드 내륙 수익 번호
이 중요한 정보 유형은 다음에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거버넌스
- 레코드 관리
- Microsoft 클라우드 앱 보안

### <a name="format"></a>형식

선택적 디지타이터가 있는 8 또는 9자리 숫자

### <a name="pattern"></a>패턴

선택적 디지타이터가 있는 8 또는 9자리 숫자

- 2-3자리 숫자
- 선택적 공백 또는 하이픈
- 3자리 숫자
- 선택적 공백 또는 하이픈
- 3자리 숫자

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이 Func_new_zealand_inland_revenue_number 패턴과 일치하는 콘텐츠를 검색합니다.
- 검색된 Keywords_new_zealand_inland_revenue_number 발견됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 이 Func_new_zealand_inland_revenue_number 패턴과 일치하는 콘텐츠를 검색합니다.

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

- ird 아니요.
- ird no #
- nz ird
- 뉴질랜드 ird
- ird 번호
- 내륙 수익 번호


## <a name="new-zealand-ministry-of-health-number"></a>뉴질랜드 보건부 번호

### <a name="format"></a>형식

3개의 문자와 4자리 숫자

### <a name="pattern"></a>패턴

- 'I' 및 'O'를 제외한 3개의 문자(대소문자 구분 안 )
- 4자리 숫자

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- Func_new_zealand_ministry_of_health_number 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_nz_terms의 키워드가 발견되었습니다.
- 체크섬이 통과됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- Func_new_zealand_ministry_of_health_number 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- 체크섬이 통과됩니다.

```xml
    <!-- New Zealand Health Number -->
    <Entity id="2b71c1c8-d14e-4430-82dc-fd1ed6bf05c7" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_new_zealand_ministry_of_health_number" />
          <Match idRef="Keyword_nz_terms" />
      </Pattern>
      <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_new_zealand_ministry_of_health_number" />
       </Pattern>
    </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_nz_terms"></a>Keyword_nz_terms

- NHI
- New Zealand
- 국가 건강 인덱스
- NHI #
- 국가 건강 인덱스 #

## <a name="new-zealand-social-welfare-number"></a>뉴질랜드 사회 일지 번호

이 중요한 정보 유형은 다음에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거버넌스
- 레코드 관리
- Microsoft 클라우드 앱 보안

### <a name="format"></a>형식

9자리 숫자

### <a name="pattern"></a>패턴

9자리 숫자

- 3자리 숫자
- 선택적 하이픈
- 3자리 숫자
- 선택적 하이픈
- 3자리 숫자

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이 Func_newzealand_social_welfare_number 일치하는 콘텐츠를 검색합니다.
- 검색된 Keywords_newzealand_social_welfare_number 발견됩니다.

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있다는 신뢰도는 낮습니다.
- 이 Func_newzealand_social_welfare_number 일치하는 콘텐츠를 검색합니다.

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

- social social #
- social social #
- social social social no.
- social social social number
- swn #


## <a name="norway-identification-number"></a>노르웨이 ID 번호

### <a name="format"></a>형식

11자리 숫자

### <a name="pattern"></a>패턴

11자리 숫자:
- 생년월일인 DDMMYY 형식의 6자리 숫자
- 3자리 개별 번호
- 검사 숫자 2개

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이 Func_norway_id_number 일치하는 콘텐츠를 검색합니다.
- 검색된 Keyword_norway_id_number 발견됩니다.
- 체크섬이 통과됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 이 Func_norway_id_numbe 패턴과 일치하는 콘텐츠를 검색합니다.
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
- Identification
- Personnummer
- Fødselsnummer


## <a name="philippines-unified-multi-purpose-identification-number"></a>필리핀 통합 다목적 ID 번호

### <a name="format"></a>형식

하이픈으로 구분된 12자리 숫자

### <a name="pattern"></a>패턴

12자리 숫자:
- 4자리 숫자
- 하이픈
- 7자리 숫자
- 하이픈
- 1자리 숫자

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 정규식 Regex_philippines_unified_id 일치하는 콘텐츠를 검색합니다.
- 검색된 Keyword_philippines_id 발견됩니다.

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

### <a name="format"></a>형식

슬래시 2개가 포함된 14자리 숫자

### <a name="pattern"></a>패턴

14자리 숫자와 슬래시 2개:

- 5자리 숫자
- 슬래시
- 2자리 숫자
- 슬래시
- 7자리 숫자

### <a name="checksum"></a>체크섬

아니요

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- `Regex_poland_eu_driver's_license_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_driver's_license_number` `Keywords_poland_eu_driver's_license_number` 찾거나 찾은 경우

```xml
      <!-- Poland Driver's License Number -->
      <Entity id="24d51f99-ee9e-4060-a077-cae58cab1ee4" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_poland_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv 라이선스
- driv 라이선스
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl 번호


#### <a name="keywords_poland_eu_drivers_license_number"></a>Keywords_poland_eu_driver s_license_number

- prawo jazdy
- prawa jazdy

## <a name="poland-identity-card"></a>폴란드 ID 카드

### <a name="format"></a>형식

3개의 문자와 6자리 숫자

### <a name="pattern"></a>패턴

3개의 문자(대소문자 구분 안 ), 6자리 숫자

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
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
- Numer dowodu osobistego
- Nazwa i numer dowodu osobistego
- Nazwa i nr dowodu osobistego
- Nazwa i nr dowodu tożsamości
- Dowód Tożsamości
- dow. os.



## <a name="poland-national-id-pesel"></a>폴란드 국가 ID(PESEL)

### <a name="format"></a>형식

11자리 숫자

### <a name="pattern"></a>패턴

- YYMMDD 형식의 생년월일을 나타내는 6자리 숫자
- 4자리 숫자
- 검사 숫자 1개

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- Func_pesel_identification_number 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_pesel_identification_number의 키워드가 발견되었습니다.
- 체크섬이 통과됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
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
- dowódosobisty
- niepowtarzalny numer
- niepowtarzalnynumer
- nr.-pesel
- nr-pesel
- numer identyfikacyjny
- pesel
- tożsamości narodowej


## <a name="poland-passport-number"></a>폴란드 여권 번호
이 중요한 정보 유형 엔터티는 EU 여권 번호 중요한 정보 유형에 포함됩니다. 독립 실행형 중요한 정보 유형 엔터티로도 사용할 수 있습니다.

### <a name="format"></a>형식

2개의 문자와 7자리 숫자

### <a name="pattern"></a>패턴

2개의 문자(대소문자 구분 안 ), 7자리 숫자

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이 `Func_polish_passport_number_v2` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 체크섬이 통과됩니다.
- 키워드를 `Keywords_eu_passport_number` `Keyword_polish_national_passport_number` 찾거나 찾은 경우
- 시작 `Keywords_eu_passport_date` 키워드가 발견됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 이 `Func_polish_passport_number_v2` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 체크섬이 통과됩니다.
- 키워드를 `Keywords_eu_passport_number` `Keyword_polish_national_passport_number` 찾거나 찾은 경우

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있다는 신뢰도는 낮습니다.
- 이 `Func_polish_passport_number_v2` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 체크섬이 통과됩니다.

```xml
      <!-- Poland Passport Number -->
      <Entity id="03937FB5-D2B6-4487-B61F-0F8BFF7C3517" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_passport_number_v2" />
          <Match idRef="Keywords_eu_passport_date" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_polish_national_passport_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_polish_passport_number_v2" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_polish_national_passport_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_polish_passport_number_v2" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keyword_polish_national_passport_number"></a>Keyword_polish_national_passport_number

- numer paszportu
- numery paszportów
- numery paszportowe
- nr paszportu
- nr. paszportu
- nr paszportów
- n° passeport
- passeport n°

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 문제의 날짜
- 만료 날짜


## <a name="poland-regon-number"></a>폴란드 REGON 번호
이 중요한 정보 유형은 다음에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거버넌스
- 레코드 관리
- Microsoft 클라우드 앱 보안

### <a name="format"></a>형식

9자리 또는 14자리 숫자

### <a name="pattern"></a>패턴

9자리 또는 14자리 숫자:

- 9자리 숫자 또는
- 9자리 숫자
- 하이픈
- 5자리 숫자

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이 Func_polish_regon_number 패턴과 일치하는 콘텐츠를 검색합니다.
- 검색된 Keywords_polish_regon_number 발견됩니다.

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있다는 신뢰도는 낮습니다.
- 이 Func_polish_regon_number 패턴과 일치하는 콘텐츠를 검색합니다.

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

- regon id
- 통계 번호
- statistical id
- statistical no
- regon number
- regonid #
- regonno #
- company id
- companyid #
- companyidno #
- numer statystyczny
- numeru regon
- numerstatystyczny #
- numeruregon #


## <a name="poland-tax-identification-number"></a>폴란드 세금 ID 번호
이 중요한 정보 유형은 다음에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거버넌스
- 레코드 관리
- Microsoft 클라우드 앱 보안

### <a name="format"></a>형식

공백이나 디지타이터가 없는 11자리 숫자

### <a name="pattern"></a>패턴

11자리 숫자

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이  `Func_poland_eu_tax_file_number` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 시작  `Keywords_poland_eu_tax_file_number` 키워드가 발견됩니다.


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
- numer identyfikacji podatkowej
- numeridentyfikacjipodatkowej #
- tax id
- tax identification no
- tax identification number
- tax no #
- tax no
- tax number
- tax registration number
- 에 대한 나타 #
- 일자 #
- 일자 수 #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #
- vat id #
- vat id
- vat no
- vat number
- vatid #
- vatid
- vatno #


## <a name="portugal-citizen-card-number"></a>포르투갈 시민 카드 번호

### <a name="format"></a>형식

8자리 숫자

### <a name="pattern"></a>패턴

8자리 숫자

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 정규식 Regex_portugal_citizen_card 일치하는 콘텐츠를 검색합니다.
- 검색된 Keyword_portugal_citizen_card 발견됩니다.

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
- citizen card
- 문서 번호
- documento de identificação
- id number
- identification no
- identification number
- ID card no
- ID 카드 번호
- national id card
- nic
- número bi de portugal
- número de identificação civil
- número de identificação 회계
- número do documento
- 포르투갈 bi number


## <a name="portugal-drivers-license-number"></a>포르투갈 운전 면허 번호

### <a name="format"></a>형식

두 개의 패턴 - 문자 2개와 특수 문자가 있는 5-8자리 숫자

### <a name="pattern"></a>패턴

패턴 1: 문자 2개와 특수 문자가 있는 5/6
- 2개 문자(대소문자 구분 안 )
- 하이픈
- 5 또는 6자리 숫자
- 공백
- 1자리 숫자

패턴 2: 문자 1개와 특수 문자가 있는 6/8자리 숫자:
- 1개 문자(대소문자 구분 안 )
- 하이픈
- 6 또는 8자리 숫자
- 공백
- 1자리 숫자


### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- `Regex_portugal_eu_driver's_license_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_driver's_license_number` `Keywords_portugal_eu_driver's_license_number` 찾거나 찾은 경우

```xml
      <!-- Portugal Driver's License Number -->
      <Entity id="977f1e5a-2c33-4bcc-b516-95bb275cff23" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_portugal_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv 라이선스
- driv 라이선스
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl 번호


#### <a name="keywords_portugal_eu_drivers_license_number"></a>Keywords_portugal_eu_driver s_license_number

- carteira de motorista
- carteira motorista
- carteira de habilitação
- carteira habilitação
- número de licença
- número licença
- permissão de condução
- permissão condução
- Licença condução Portugal
- carta de condução

## <a name="portugal-passport-number"></a>포르투갈 여권 번호

### <a name="format"></a>형식

공백이나 따로 6자리 숫자를 입력하고 공백이나 따로 문자를 1개씩 입력합니다.

### <a name="pattern"></a>패턴

한 문자와 6자리 숫자:

- 한 문자(대소문자 구분 안 )
- 6자리 숫자

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- `Regex_portugal_eu_passport_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_passport_number` `Keywords_portugal_eu_passport_number` 찾거나 찾은 경우
- `Regex_eu_passport_date1`정규식이 DD.MM.YYYY 형식의 날짜를 찾거나 키워드를 `Keywords_eu_passport_date` 찾은 경우

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- `Regex_portugal_eu_passport_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_passport_number` `Keywords_portugal_eu_passport_number` 찾거나 찾은 경우

```xml
      <!-- Portugal Passport Number -->
      <Entity id="080a52fd-a7bc-431e-b54d-51f08f59db11" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_portugal_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_portugal_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_portugal_eu_passport_number"></a>Keywords_portugal_eu_passport_number

- número do passaporte
- 포르투갈 여권
- 포르투갈어(passeport)
- 포르투갈어(passaporte)
- passaporte nº
- passeport nº
- números de passaporte
- 포르투갈 여권
- número passaporte
- números passaporte

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 문제의 날짜
- 만료 날짜


## <a name="portugal-tax-identification-number"></a>포르투갈 세금 ID 번호

### <a name="format"></a>형식

선택적 공백이 있는 9자리 숫자

### <a name="pattern"></a>패턴

- 3자리 숫자
- 선택적 공백
- 3자리 숫자
- 선택적 공백
- 3자리 숫자

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이  `Func_portugal_eu_tax_file_number` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 시작  `Keywords_portugal_eu_tax_file_number` 키워드가 발견됩니다.

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있다는 신뢰도는 낮습니다.
- 이  `Func_portugal_eu_tax_file_number` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.

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
- nif #
- nif
- número de identificação fisca
- numero 회계
- tax id
- tax identification no
- tax identification number
- tax no #
- tax no
- tax number
- tax registration number
- 에 대한 나타 #
- 일자 #
- 일자 수 #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #


## <a name="romania-drivers-license-number"></a>루마니아 운전 면허 번호

### <a name="format"></a>형식

문자 1개와 숫자 8자

### <a name="pattern"></a>패턴

한 문자와 8자리 숫자:
- 한 문자(대소문자 구분 안 되거나 숫자)
- 8자리 숫자

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- `Regex_romania_eu_driver's_license_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_driver's_license_number` `Keywords_romania_eu_driver's_license_number` 찾거나 찾은 경우

```xml
      <!-- Romania Driver's License Number -->
      <Entity id="b5511ace-2fd8-4ae4-b6fc-c7c6e4689e3c" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_romania_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv 라이선스
- driv 라이선스
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl 번호


#### <a name="keywords_romania_eu_drivers_license_number"></a>Keywords_romania_eu_driver s_license_number

- permis de conducere
- permisului de conducere
- permisului conducere
- permisele de conducere
- permisele conducere
- permis conducere

## <a name="romania-personal-numeric-code-cnp"></a>루마니아 CNP(개인 번호)
이 중요한 정보 유형은 다음에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거버넌스
- 레코드 관리
- Microsoft 클라우드 앱 보안

### <a name="format"></a>형식

공백 및 디지타이터가 없는 13자리 숫자

### <a name="pattern"></a>패턴

- 1-9에서 1자리 숫자
- 생년월일을 나타내는 6자리 숫자(YYMMDD)
- 01-52 또는 99일 수 있는 2자리 숫자
- 4자리 숫자

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이  `Func_romania_eu_national_id_card` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 시작  `Keywords_romania_eu_national_id_card` 키워드가 발견됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 이  `Func_romania_eu_national_id_card` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.

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
- codul 회계 nr.
- identificarea fiscală nr #
- id-ul taxei
- insurance number
- insurancenumber #
- national id #
- national id
- national identification number
- număr identificare personal
- număr IDentitate
- număr personal unic
- număridentitate #
- număridentitate
- numărpersonalunic #
- numărpersonalunic
- număru de identificare fiscală
- numărul de identificare fiscală
- 개인 숫자 코드
- 핀 #
- 핀
- tax file no
- tax file number
- tax id
- tax identification no
- tax identification number
- tax no #
- tax no
- tax number
- tax registration number
- 에 대한 나타 #
- 일자 #
- 일자 수 #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #
- 고유 ID 번호
- 고유 ID 번호
- uniqueidentityno #
- uniqueidentityno

## <a name="romania-passport-number"></a>루마니아 여권 번호

### <a name="format"></a>형식

공백 및 디지타이터가 없는 8 또는 9자리 숫자

### <a name="pattern"></a>패턴

8자리 또는 9자리 숫자

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- `Regex_romania_eu_passport_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_passport_number` `Keywords_romania_eu_passport_number` 찾거나 찾은 경우
- `Regex_romania_eu_passport_date`정규식은 DD MMM/MMM YY(예제- 01 FEB/FEB 10) 형식의 날짜를 찾거나 키워드가 `Keywords_eu_passport_date` 발견되었습니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- `Regex_romania_eu_passport_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_passport_number` `Keywords_romania_eu_passport_number` 찾거나 찾은 경우

```xml
      <!-- Romania Passport Number -->
      <Entity id="5d31b90c-7fe2-4a76-a14b-767b8fd19d6c" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_romania_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_romania_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_romania_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_romania_eu_passport_number"></a>Keywords_romania_eu_passport_number

numărul pașaportului numarul pasaportului numerele pașaportului Pașaport nr

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 문제의 날짜
- 만료 날짜


## <a name="russia-passport-number-domestic"></a>러시아 여권 번호 국내
이 중요한 정보 유형은 다음에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거버넌스
- 레코드 관리
- Microsoft 클라우드 앱 보안

### <a name="format"></a>형식

10자리 숫자

### <a name="pattern"></a>패턴

10자리 숫자:

- 2자리 숫자
- 선택적 공백 또는 하이픈
- 2자리 숫자
- 선택적 공백
- 6자리 숫자

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- regex Regex_Russian_Passport_Number_Domestic 패턴과 일치하는 콘텐츠를 검색합니다.
- 검색된 Keyword_Russian_Passport_Number 발견됩니다.

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

- passport number
- passport no
- passport #
- passport id
- passportno #
- passportnumber #
- паспорт нет
- паспорт id
- pоссийской паспорт
- pусский номер паспорта
- паспорт #
- паспортid #
- номер паспорта
- номерпаспорта #


## <a name="russia-passport-number-international"></a>러시아 여권 번호 국제
이 중요한 정보 유형은 다음에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거버넌스
- 레코드 관리
- Microsoft 클라우드 앱 보안

### <a name="format"></a>형식

9자리 숫자

### <a name="pattern"></a>패턴

9자리 숫자:

- 2자리 숫자
- 선택적 공백 또는 하이픈
- 7자리 숫자

### <a name="checksum"></a>체크섬

아니요

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- regex Regex_Russian_Passport_Number_International 패턴과 일치하는 콘텐츠를 검색합니다.
- 검색된 Keyword_Russian_Passport_Number 발견됩니다.

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

- passport number
- passport no
- passport #
- passport id
- passportno #
- passportnumber #
- паспорт нет
- паспорт id
- pоссийской паспорт
- pусский номер паспорта
- паспорт #
- паспортid #
- номер паспорта
- номерпаспорта #


## <a name="saudi-arabia-national-id"></a>사우디 아라비아 국가 ID

### <a name="format"></a>형식

10자리 숫자

### <a name="pattern"></a>패턴

10자리 연속 숫자

### <a name="checksum"></a>체크섬

아니요

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
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


## <a name="singapore-national-registration-identity-card-nric-number"></a>싱가포르 NRIC(국가 등록 ID 카드) 번호

### <a name="format"></a>형식

9개의 문자 및 숫자

### <a name="pattern"></a>패턴

- 9개의 문자 및 숫자:
- 문자 "F", "G", "S" 또는 "T"(대소문자를 구분하지 않습니다.)
- 7자리 숫자
- 사전순 검사 숫자

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 정규식은 Regex_singapore_nric 일치하는 콘텐츠를 검색합니다.
- 검색된 Keyword_singapore_nric 발견됩니다.
- 체크섬이 통과됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 정규식은 Regex_singapore_nric 일치하는 콘텐츠를 검색합니다.
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
- IC
- Foreign Identification Number
- FIN
- 身份证
- 身份證

## <a name="slovakia-drivers-license-number"></a>슬로바키아 운전 면허 번호

### <a name="format"></a>형식

한 문자와 7자리 숫자

### <a name="pattern"></a>패턴

한 문자와 7자리 숫자

- 한 문자(대소문자 구분 안 되거나 숫자)
- 7자리 숫자

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- `Regex_slovakia_eu_driver's_license_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_driver's_license_number` `Keywords_slovakia_eu_driver's_license_number` 찾거나 찾은 경우

```xml
      <!-- Slovakia Driver's License Number -->
      <Entity id="14240c22-b6de-4ce5-a90b-137f74252513" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv 라이선스
- driv 라이선스
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl 번호


#### <a name="keywords_slovakia_eu_drivers_license_number"></a>Keywords_slovakia_eu_driver s_license_number

- vodičský preukaz
- vodičské preukazy
- vodičského preukazu
- vodičských preukazov

## <a name="slovakia-personal-number"></a>슬로바키아 개인 번호
이 중요한 정보 유형은 다음에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거버넌스
- 레코드 관리
- Microsoft 클라우드 앱 보안

### <a name="format"></a>형식

선택적 백 슬래시를 포함하는 9자리 또는 10자리 숫자

### <a name="pattern"></a>패턴

- 생년월일을 나타내는 6자리 숫자
- 선택적 슬래시(/)
- 3자리 숫자
- 선택적 검사 숫자 1개

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이  `Func_slovakia_eu_national_id_card` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 시작  `Keywords_slovakia_eu_national_id_card` 키워드가 발견됩니다.

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있다는 신뢰도는 낮습니다.
- 이  `Func_slovakia_eu_national_id_card` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.

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

- azonosító szám
- birth number
- číslo národnej identifikačnej karty
- číslo občianského preukazu
- daňové číslo
- id number
- identification no
- identification number
- identifikačná karta č
- identifikačné číslo
- ID card no
- ID 카드 번호
- národná identifikačná značka č
- national number
- nationalnumber #
- nemzeti személyazonosító igazolvány
- personalidnumber #
- rč
- rodne cislo
- rodné číslo
- social security number
- ssn #
- ssn
- személyi igazolvány szám
- személyi igazolvány száma
- személyigazolvány szám
- tax file no
- tax file number
- tax id
- tax identification no
- tax identification number
- tax no #
- tax no
- tax number
- tax registration number
- 에 대한 나타 #
- 일자 #
- 일자 수 #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #

## <a name="slovakia-passport-number"></a>슬로바키아 여권 번호

### <a name="format"></a>형식

공백이나 공백이 없는 7자리 숫자

### <a name="pattern"></a>패턴

1자리 숫자 또는 문자(대소문자 구분 안 ), 7자리 숫자

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- `Regex_slovakia_eu_passport_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_passport_number` `Keywords_slovakia_eu_passport_number` 찾거나 찾은 경우
- `Regex_eu_passport_date1`정규식이 DD.MM.YYYY 형식의 날짜를 찾거나 키워드를 `Keywords_eu_passport_date` 찾은 경우

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- `Regex_slovakia_eu_passport_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_passport_number` `Keywords_slovakia_eu_passport_number` 찾거나 찾은 경우

```xml
      <!-- Slovakia Passport Number -->
      <Entity id="238e1f08-d80e-4793-af33-9b57918335b7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_slovakia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_slovakia_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_slovakia_eu_passport_number"></a>Keywords_slovakia_eu_passport_number

- číslo pasu
- čísla pasov
- pas č.
- Passeport n°
- n° Passeport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 문제의 날짜
- 만료 날짜


## <a name="slovenia-drivers-license-number"></a>스로베니아 운전 면허 번호

### <a name="format"></a>형식

공백 및 디지타이터가 없는 9자리 숫자

### <a name="pattern"></a>패턴

9자리 숫자

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- `Regex_slovenia_eu_driver's_license_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_driver's_license_number` `Keywords_slovenia_eu_driver's_license_number` 찾거나 찾은 경우

```xml
      <!-- Slovenia Driver's License Number -->
      <Entity id="d5bc089a-f2ee-433d-a6b1-5c253051d6f2" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv 라이선스
- driv 라이선스
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl 번호


#### <a name="keywords_slovenia_eu_drivers_license_number"></a>Keywords_slovenia_eu_driver s_license_number

- vozniško dovoljenje
- vozniška številka licence
- vozniških dovoljenj
- številka vozniškega dovoljenja
- številke vozniških dovoljenj

## <a name="slovenia-unique-master-citizen-number"></a>Slovenia Unique Master Citizen Number

이 중요한 정보 유형은 다음에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거버넌스
- 레코드 관리
- Microsoft 클라우드 앱 보안

### <a name="format"></a>형식

공백이나 디지타이터가 없는 13자리 숫자

### <a name="pattern"></a>패턴

지정된 패턴의 13자리 숫자:

- "LLL"이 생년월일의 마지막 3자리에 해당하는 생년월일(DDMMLLL)에 해당하는 7자리 숫자
- 생년월일 "50"에 해당하는 2자리 숫자
- 같은 날에 태어나는 사람의 성별과 일련 번호 조합에 해당하는 세 자리 숫자입니다. 남성의 경우 000-499, 여성의 경우 500-999입니다.
- 검사 숫자 1개

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이  `Func_slovenia_eu_national_id_card` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 시작  `Keywords_slovenia_eu_national_id_card` 키워드가 발견됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 이  `Func_slovenia_eu_national_id_card` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.

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

- edinstvena številka glavnega državljana
- emšo
- enotna maticna številka obcana
- id card
- identification number
- identifikacijska številka
- identity card
- nacionalna id
- nacionalni potni 목록
- national id
- osebna izkaznica
- osebni koda
- osebni ne
- osebni številka
- 개인 코드
- personal number
- 개인 숫자 코드
- številka državljana
- 고유 시민 번호
- 고유 ID 번호
- 고유 ID 번호
- 고유 마스터 시민 번호
- 고유 등록 번호
- uniqueidentityno #
- uniqueidentityno #

## <a name="slovenia-passport-number"></a>솔로베니아 여권 번호

### <a name="format"></a>형식

공백이나 따로 7자리 숫자를 입력할 때 공백이나 공백이 없는 문자 2개

### <a name="pattern"></a>패턴

2개의 문자와 7자리 숫자:

- 문자 "P"
- 대문자 1개
- 7자리 숫자

### <a name="checksum"></a>체크섬

아니요

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- `Regex_slovenia_eu_passport_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_passport_number` `Keywords_slovenia_eu_passport_number` 찾거나 찾은 경우
- `Regex_eu_passport_date1`정규식이 DD.MM.YYYY 형식의 날짜를 찾거나 키워드를 `Keywords_eu_passport_date` 찾은 경우

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- `Regex_slovenia_eu_passport_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_passport_number` `Keywords_slovenia_eu_passport_number` 찾거나 찾은 경우

```xml
      <!-- Slovenia Passport Number -->
      <Entity id="235b7976-7bbe-4df5-bb40-08678e749d1a" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_slovenia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_slovenia_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_slovenia_eu_passport_number"></a>Keywords_slovenia_eu_passport_number

- številka potnega lista
- potek veljavnosti
- potni 목록 #
- datum rojstva
- potni 목록
- številke potnih listov

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 문제의 날짜
- 만료 날짜


## <a name="slovenia-tax-identification-number"></a>솔로베니아 세금 식별 번호
이 중요한 정보 유형은 다음에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거버넌스
- 레코드 관리
- Microsoft 클라우드 앱 보안

### <a name="format"></a>형식

공백이나 디지타이터가 없는 8자리 숫자

### <a name="pattern"></a>패턴

- 1-9에서 1자리 숫자
- 6자리 숫자
- 검사 숫자 1개

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이  `Func_slovenia_eu_tax_file_number` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 시작  `Keywords_slovenia_eu_tax_file_number` 키워드가 발견됩니다.

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있다는 신뢰도는 낮습니다.
- 이  `Func_slovenia_eu_tax_file_number` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.

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

- davčna številka
- identifikacijska številka davka
- številka davčne datoteke
- tax file no
- tax file number
- tax id
- tax identification no
- tax identification number
- tax no #
- tax no
- tax number
- tax registration number
- 에 대한 나타 #
- 일자 #
- 일자 수 #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #


## <a name="south-africa-identification-number"></a>남아프리카 공화국 ID 번호

### <a name="format"></a>형식

공백을 포함할 수 있는 13자리 숫자

### <a name="pattern"></a>패턴

13자리 숫자:
- 생년월일인 YYMMDD 형식의 6자리 숫자
- 4자리 숫자
- 한 자리 숫자 시민권 표시기
- 숫자 "8" 또는 "9"
- 체크 um 숫자인 1자리 숫자

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이 Func_south_africa_identification_number 패턴과 일치하는 콘텐츠를 검색합니다.
- 검색된 Keyword_south_africa_identification_number 발견됩니다.
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
- Identification

## <a name="south-korea-resident-registration-number"></a>대한민국 거주자 등록 번호

### <a name="format"></a>형식

하이픈을 포함하는 13자리 숫자

### <a name="pattern"></a>패턴

13자리 숫자:
- 생년월일인 YYMMDD 형식의 6자리 숫자
- 하이픈
- 세기 및 성별로 결정된 1자리 숫자
- 4자리 생년월일 코드
- 앞의 숫자가 동일한 사람들을 차별화하는 데 사용되는 한 자리 숫자
- 검사 숫자입니다.

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이 Func_south_korea_resident_number 일치하는 콘텐츠를 검색합니다.
- 검색된 Keyword_south_korea_resident_number 발견됩니다.
- 체크섬이 통과됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 이 Func_south_korea_resident_number 일치하는 콘텐츠를 검색합니다.
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

### <a name="format"></a>형식

8자리 숫자와 한 문자

### <a name="pattern"></a>패턴

8자리 숫자와 문자 1자:

- 8자리 숫자
- 1자리 숫자 또는 문자(대소문자 구분 안 )

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 함수가  `Func_spain_eu_DL_and_NI_number_citizen` `Func_spain_eu_DL_and_NI_number_foreigner` 해당 패턴과 일치하는 콘텐츠를 찾거나 검색합니다.
- 키워드를  `Keywords_eu_driver's_license_number` `Keywords_spain_eu_driver's_license_number` 찾거나 찾은 경우

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 함수가  `Func_spain_eu_DL_and_NI_number_citizen` `Func_spain_eu_DL_and_NI_number_foreigner` 해당 패턴과 일치하는 콘텐츠를 찾거나 검색합니다.

```xml
      <!-- Spain Driver's License Number -->
      <Entity id="d5a82922-b501-4f40-8868-341321146aa2" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_spain_eu_driver's_license_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
        </Pattern>
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_foreigner" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_spain_eu_driver's_license_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_foreigner" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv 라이선스
- driv 라이선스
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl 번호


#### <a name="keywords_spain_eu_drivers_license_number"></a>Keywords_spain_eu_driver s_license_number

- permiso de conducción
- permiso conducción
- licencia de conducir
- licencia conducir
- permiso conducir
- permiso de conducir
- permisos de conducir
- permisos conducir
- carnet conducir
- carnet de conducir
- licencia de manejo
- licencia manejo

## <a name="spain-dni"></a>스페인 DNI

이 중요한 정보 유형은 다음에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거버넌스
- 레코드 관리
- Microsoft 클라우드 앱 보안

### <a name="format"></a>형식

8자리 숫자와 한 문자

### <a name="pattern"></a>패턴

7자리 숫자와 문자 1자

- 8자리 숫자
- 선택적 공백 또는 하이픈
- 검사 문자 1개(대소문자 구분 안 )

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 함수가  `Func_spain_eu_DL_and_NI_number_citizen` `Func_spain_eu_DL_and_NI_number_foreigner` 해당 패턴과 일치하는 콘텐츠를 찾거나 검색합니다.
- 시작  `Keywords_spain_eu_national_id_card"` 키워드가 발견됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 함수가  `Func_spain_eu_DL_and_NI_number_citizen` `Func_spain_eu_DL_and_NI_number_foreigner` 해당 패턴과 일치하는 콘텐츠를 찾거나 검색합니다.


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
- identidad único
- identidadúnico #
- insurance number
- national identification number
- national identity
- nationalid #
- nationalidno #
- nie #
- nie
- nienúmero #
- número de identificación
- número nacional identidad
- 개인 식별 번호
- 개인 ID 아니요
- 고유 ID 번호
- uniqueid #

## <a name="spain-passport-number"></a>스페인 여권 번호

### <a name="format"></a>형식

공백이나 디지타이터가 없는 문자와 숫자의 8자 또는 9자 조합

### <a name="pattern"></a>패턴

8자 또는 9자 조합의 문자와 숫자입니다.

- 2자리 숫자 또는 문자
- 1자리 숫자 또는 문자(선택 사항)
- 6자리 숫자

### <a name="checksum"></a>체크섬

해당 없음

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- `Regex_spain_eu_passport_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_passport_number` `Keywords_spain_eu_passport_number` 찾거나 찾은 경우
- `Regex_spain_eu_passport_date`정규식이 DD-MM-YYYY 형식의 날짜를 찾거나 키워드를 `Keywords_eu_passport_date` 찾은 경우

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- `Regex_spain_eu_passport_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_passport_number` `Keywords_spain_eu_passport_number` 찾거나 찾은 경우

```xml
      <!-- Spain Passport Number -->
      <Entity id="d17a57de-9fa5-4e9f-85d3-85c26d89686e" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_spain_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_spain_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_spain_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_spain_eu_passport_number"></a>Keywords_spain_eu_passport_number

- libreta pasaporte
- número pasaporte
- españa pasaporte
- números de pasaporte
- número de pasaporte
- números pasaporte
- pasaporte no
- Passeport n°
- n° Passeport
- pasaporte no.
- pasaporte n°
- 스페인 여권

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 문제의 날짜
- 만료 날짜


## <a name="spain-social-security-number-ssn"></a>스페인 SSN(사회 보장 번호)


### <a name="format"></a>형식

11-12자리 숫자

### <a name="pattern"></a>패턴

11-12자리 숫자:
- 2자리 숫자
- 슬래시(선택 사항)
- 7-8자리 숫자
- 슬래시(선택 사항)
- 2자리 숫자

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- Func_spanish_social_security_number 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- 체크섬이 통과됩니다.
- - 시작  `Keywords_spain_eu_ssn_or_equivalent` 키워드가 발견됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- Func_spanish_social_security_number 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- 체크섬이 통과됩니다.

```xml
    <!-- Spain SSN -->
    <Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85" relaxProximity="true" >
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spanish_social_security_number" />
          <Match idRef="Keywords_spain_eu_ssn_or_equivalent" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spanish_social_security_number" />
        </Pattern>
    </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_spain_eu_passport_number"></a>Keywords_spain_eu_passport_number

- ssn
- ssn #
- socialsecurityno
- social security no
- social security number
- número de la seguridad social

## <a name="spain-tax-identification-number"></a>스페인 세금 ID 번호
이 중요한 정보 유형은 다음에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거버넌스
- 레코드 관리
- Microsoft 클라우드 앱 보안

### <a name="format"></a>형식

지정된 패턴에서 7-8자리 숫자와 1-2자리 문자

### <a name="pattern"></a>패턴

스페인 국가 ID 카드가 있는 스페인어 자연인:

- 8자리 숫자
- 대문자 1개(대소문자 구분)

스페인 국가 ID 카드가 없는 비 거주자 Spaniards

- 대문자 1자 "L"(대소문자 구분)
- 7자리 숫자
- 대문자 1개(대소문자 구분)

스페인 국가 ID 카드가 없는 14세 미만의 거주자:

- 대문자 1자 "K"(대소문자 구분)
- 7자리 숫자
- 대문자 1개(대소문자 구분)

Foreigners with a Foreigner's Identification Number

- "X", "Y" 또는 "Z"(대소문자 구분)의 대문자 하나
- 7자리 숫자
- 대문자 1개(대소문자 구분)

Foreigners without a Foreigner's Identification Number

- "M"을(를) 구분하는 대문자 1개
- 7자리 숫자
- 대문자 1개(대소문자 구분)

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 함수가  `Func_spain_eu_tax_file_number` `Func_spain_eu_DL_and_NI_number_citizen` 해당 패턴과 일치하는 콘텐츠를 찾거나 검색합니다.
- 시작  `Keywords_spain_eu_tax_file_number` 키워드가 발견됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 함수가  `Func_spain_eu_tax_file_number` `Func_spain_eu_DL_and_NI_number_citizen` 해당 패턴과 일치하는 콘텐츠를 찾거나 검색합니다.

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
- tax file no
- tax file number
- tax id
- tax identification no
- tax identification number
- tax no #
- tax no
- tax number
- tax registration number
- 에 대한 나타 #
- 일자 #
- 일자 수 #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #


## <a name="sql-server-connection-string"></a>SQL Server 연결 문자열

### <a name="format"></a>형식

문자열 "User Id", "User ID", "uid" 또는 "UserId" 다음에 아래 패턴에 설명된 문자와 문자열입니다.

### <a name="pattern"></a>패턴

- 문자열 "User Id", "User ID", "uid" 또는 "UserId"
- 1에서 200 사이의 대문자, 숫자, 기호, 특수 문자 또는 공백의 조합
- 문자열 "Password" 또는 "pwd"에서 "pwd"는 소문자 앞에 있지 않습니다.
- 등호(=)
- 달러 기호($), 백분율 기호(%), 기호(>), 기호(@), 인용 부호("), 세미코론(;), 왼쪽 중괄호([) 또는 왼쪽 대괄호({)가 아닌 모든 문자
- 세미코론(;), 슬래시(/) 또는 인용 부호(")가 아닌 7-128자 조합
- 세미코론(;) 또는 인용 부호(")

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 정규식 CEP_Regex_SQLServerConnectionString 일치하는 콘텐츠를 검색합니다.
- 검색된 CEP_GlobalFilter 찾을 수 없습니다.
- 정규식 CEP_PasswordPlaceHolder 일치하는 콘텐츠를 찾을 수 없습니다.
- 정규식 CEP_CommonExampleKeywords 일치하는 콘텐츠를 찾을 수 없습니다.

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

- some-password
- somepassword
- secretPassword
- sample

#### <a name="cep_passwordplaceholder"></a>CEP_PasswordPlaceHolder

이 중요한 정보 유형은 키워드 목록이 아닌 정규식을 사용하여 이러한 키워드를 식별합니다.

- 암호 또는 pwd 다음에 0-2 공백, 등호(=), 0-2 공백 및 추가 표시(*) -OR-
- 암호 또는 pwd 다음을 입력합니다.
    - 등호(=)
    - 기호(<)
    - 대/소문자, 숫자, 추가 문자(*), 하이픈(-), 밑 줄(_) 또는 공백 문자에 대한 1-200자 조합
    - 기호보다 크다(>)

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

이 중요한 정보 유형은 키워드 목록이 아닌 정규식을 사용하여 이러한 키워드를 식별합니다.

- contoso
- fabrikam
- northwind
- 샌드박스
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="sweden-drivers-license-number"></a>스웨덴 운전 면허 번호

### <a name="format"></a>형식

하이픈을 포함하는 10자리 숫자

### <a name="pattern"></a>패턴

하이픈을 포함하는 10자리 숫자:

- 6자리 숫자
- 하이픈
- 4자리 숫자

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- `Regex_sweden_eu_driver's_license_number`정규식이 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를  `Keywords_eu_driver's_license_number` `Keywords_sweden_eu_driver's_license_number` 찾거나 찾은 경우

```xml
      <!-- Sweden Driver's License Number -->
      <Entity id="70088720-90dd-47f5-805e-5525f3567391" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_sweden_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv 라이선스
- driv 라이선스
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl 번호


#### <a name="keywords_sweden_eu_drivers_license_number"></a>Keywords_sweden_eu_driver s_license_number

- ajokortti
- permis de conducere
- ajokortin numero
- kuljettajat lic.
- drivere lic.
- körkort
- numărul permisului de conducere
-  שאָפער דערלויבעניש נומער
- förare lic.
-  דריווערס דערלויבעניש
- körkortsnummer

## <a name="sweden-national-id"></a>스웨덴 국가 ID

### <a name="format"></a>형식

10 또는 12자리 숫자와 선택적 구분 기호

### <a name="pattern"></a>패턴

10 또는 12자리 숫자와 선택적 구분 기호:
- 두 자리 숫자(선택 사항)
- YYMMDD 날짜 형식의 6자리 숫자
- delimiter of "-" or "+" (optional)
- 4자리 숫자

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이 `Func_swedish_national_identifier` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 키워드를 `Keywords_swedish_national_identifier` 찾은 경우
- 체크섬이 통과됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 이 `Func_swedish_national_identifier` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.
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

- id no
- id number
- id #
- identification no
- identification number
- identifikationsnumret #
- identifikationsnumret
- identitetshandling
- ID 문서
- IDENTITY no
- ID 번호
- id-nummer
- personal id
- personnummer #
- personnummer
- skatteidentifikationsnummer

## <a name="sweden-passport-number"></a>스웨덴 여권 번호

### <a name="format"></a>형식

8자리 숫자

### <a name="pattern"></a>패턴

8자리 연속 숫자

### <a name="checksum"></a>체크섬

아니요

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 정규식 Regex_sweden_passport_number 일치하는 콘텐츠를 검색합니다.
- 키워드를 `Keywords_eu_passport_number` `Keyword_sweden_passport` 찾거나 찾은 경우
- `Regex_sweden_eu_passport_date`정규식이 DD MMM/MMM YY(01 JAN/JAN 12) 형식의 날짜를 찾거나 키워드가 `Keywords_eu_passport_date` 발견되었습니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 정규식 Regex_sweden_passport_number 일치하는 콘텐츠를 검색합니다.
- 키워드를 `Keywords_eu_passport_number` `Keyword_sweden_passport` 찾거나 찾은 경우


```xml
    <!-- Sweden Passport Number -->
    <Entity id="ba4e7456-55a9-4d89-9140-c33673553526" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_sweden_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_sweden_passport" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_sweden_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_sweden_passport" />
          </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keyword_sweden_passport"></a>Keyword_sweden_passport

- 에나이트 등록 카드
- g3 처리 요금
- 여러 항목
- Numéro de passeport
- passeport n °
- passeport non
- passeport #
- passeport #
- passeportnon
- passeportn °
- passnummer
- nr 전달
- schengen visa
- schengen visas
- 단일 항목
- sverige pass
- visa requirements
- visa processing
- visa type(visa type)

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 문제의 날짜
- 만료 날짜


## <a name="sweden-tax-identification-number"></a>스웨덴 세금 식별 번호
이 중요한 정보 유형은 다음에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거버넌스
- 레코드 관리
- Microsoft 클라우드 앱 보안

### <a name="format"></a>형식

지정된 패턴의 10자리 숫자 및 기호

### <a name="pattern"></a>패턴

10자리 숫자와 기호:

- 생년월일(YYMMDD)에 해당하는 6자리 숫자
- 더하기 기호 또는 마이너스 기호
- ID 번호를 고유하게 만드는 세 자리 숫자입니다. 여기서:
  - 1990년 전에 발급된 숫자의 경우 7번째와 8번째 숫자는 생년월일 또는 외계인을 식별합니다.
  - 9번째 위치의 숫자는 성별을 남성에 대해 홀수로 나타내거나 여성의 경우 조차도 나타냅니다.
- 검사 숫자 1개

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이  `Func_sweden_eu_tax_file_number` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 시작  `Keywords_sweden_eu_tax_file_number` 키워드가 발견됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 이  `Func_sweden_eu_tax_file_number` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.

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

- 개인 ID 번호
- personnummer
- nummt id nummer
- skatt identifikation
- skattebetalarens identifikationsnummer
- sverige tin
- tax file
- tax id
- tax identification no
- tax identification number
- tax no #
- tax no
- tax number
- tax registration number
- 에 대한 나타 #
- 일자 #
- 일자 수 #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #


## <a name="swift-code"></a>SWIFT 코드

### <a name="format"></a>형식

4개의 문자와 5-31개의 문자 또는 숫자

### <a name="pattern"></a>패턴

4개의 문자와 5-31개의 문자 또는 숫자:
- 4문자 은행 코드(대소문자 구분 안 )
- 선택적 공백
- 4-28개 문자 또는 숫자[BBAN(기본 은행 계좌 번호)]
- 선택적 공백
- 1~3자리 숫자(BBAN의 나머지)

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
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
- swift #
- swiftcode
- swiftnumber
- swiftroutingnumber
- swift code
- swift number #
- swift routing number
- bic number
- bic code
- bic #
- bic #
- bank identifier code
- Organisation internationale de normalisation 9362
- rapide #
- code SWIFT
- le numéro de swift
- swift numéro d'acheminement
- le numéro BIC
- # <a name="bic"></a>BIC
- code identificateur de banque
- SWIFTーー囙
- SWIFT番号
- BIC番号
- BIC 조지민 님
- SWIFT ೺囏
- SWIFT 番号
- BIC 番号
- BIC의 은(는)
- 金融機関識別コード
- 金融機関コード
- 銀行コード

## <a name="switzerland-ssn-ahv-number"></a>스위스 SSN AHV 번호
이 중요한 정보 유형은 다음에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거버넌스
- 레코드 관리
- Microsoft 클라우드 앱 보안

### <a name="format"></a>형식

13자리 숫자

### <a name="pattern"></a>패턴

13자리 숫자:

- 3자리 숫자 - 756
- 선택적 점
- 4자리 숫자
- 선택적 점
- 4자리 숫자
- 선택적 점
- 2자리 숫자

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이 Func_swiss_social_security_number_ahv 일치하는 콘텐츠를 검색합니다.
- 검색된 Keywords_swiss_social_security_number_ahv 발견됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 이 Func_swiss_social_security_number_ahv 일치하는 콘텐츠를 검색합니다.

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
- pid
- insurance number
- personalidno #
- social security number
- 개인 ID 번호
- personal identification no.
- insuranceno #
- uniqueidno #
- unique identification no.
- avs number
- personal identity no versicherungsnummer
- identifikationsnummer
- einzigartige identität nicht
- sozialversicherungsnummer
- identification personnelle id
- numéro de sécurité sociale


## <a name="taiwan-national-identification-number"></a>대만 국가 ID 번호

### <a name="format"></a>형식

1개의 문자(영어) 및 9자리 숫자

### <a name="pattern"></a>패턴

한 문자(영어) 다음에 9자리 숫자를 입력합니다.
- 한 글자(영어로, 대소문자를 구분하지 않습니다.)
- 숫자 "1" 또는 "2"
- 8자리 숫자

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- Func_taiwanese_national_id 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_taiwanese_national_id의 키워드가 발견되었습니다.
- 체크섬이 통과됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
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

### <a name="format"></a>형식

- 생체 인식 여권 번호: 9자리 숫자
- 생체 인식이 아닌 여권 번호: 9자리 숫자

### <a name="pattern"></a>패턴
생체 인식 여권 번호:
- 문자 "3"
- 8자리 숫자

생체 인식이 아닌 여권 번호:
- 9자리 숫자

### <a name="checksum"></a>체크섬

아니요

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 정규식 Regex_taiwan_passport 일치하는 콘텐츠를 검색합니다.
- 검색된 Keyword_taiwan_passport 발견됩니다.

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

## <a name="taiwan-resident-certificate-arctarc-number"></a>대만 거주 인증서(ARC/TARC) 번호

### <a name="format"></a>형식

10개의 문자 및 숫자

### <a name="pattern"></a>패턴

10개의 문자 및 숫자:
- 2개 문자(대소문자 구분 안 )
- 8자리 숫자

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 정규식은 Regex_taiwan_resident_certificate 일치하는 콘텐츠를 검색합니다.
- 검색된 Keyword_taiwan_resident_certificate 발견됩니다.

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

## <a name="thai-population-identification-code"></a>태국어 인구 ID 코드

### <a name="format"></a>형식

13자리 숫자

### <a name="pattern"></a>패턴

13자리 숫자:
- 첫 번째 숫자가 0 또는 9가 아닌 경우
- 12자리 숫자

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이 Func_Thai_Citizen_Id 패턴과 일치하는 콘텐츠를 검색합니다.
- 검색된 Keyword_Thai_Citizen_Id 발견됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 이 Func_Thai_Citizen_Id 패턴과 일치하는 콘텐츠를 검색합니다.

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

- ID 번호
- Identification Number
- บัตรประชาชน
- รหัสบัตรประชาชน
- บัตรประชาชน
- รหัสบัตรประชาชน

## <a name="turkish-national-identification-number"></a>터키어 국가 ID 번호

### <a name="format"></a>형식

11자리 숫자

### <a name="pattern"></a>패턴

11자리 숫자

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이 Func_Turkish_National_Id 일치하는 콘텐츠를 검색합니다.
- 검색된 Keyword_Turkish_National_Id 발견됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 이 Func_Turkish_National_Id 일치하는 콘텐츠를 검색합니다.

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

- TC Kimlik No
- TC Kimlik numarası
- Vatandaşlık numarası
- Vatandaşlık no

## <a name="uk-drivers-license-number"></a>영국 driver's license number

### <a name="format"></a>형식

지정된 형식의 18개 문자 및 숫자 조합

### <a name="pattern"></a>패턴

18개의 문자 및 숫자:
- 5개의 문자(대소문자 구분 안 되거나 문자 대신 숫자 "9")입니다.
- 1자리 숫자
- 생년월일의 날짜 형식 MMDDY의 5자리 숫자입니다. 드라이버가 여성인 경우 일곱 번째 문자가 50으로 증가합니다. 시험의 경우 01에서 12까지가 아니라 51에서 62까지입니다.
- 대소문자 2개(대소문자 구분 안 되거나 문자 대신 숫자 "9")를 입력합니다.
- 5자리 숫자

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 이 `Func_uk_drivers_license` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 시작 `Keywords_eu_driver's_license_number` 키워드가 발견됩니다.
- 체크섬이 통과됩니다.

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있다는 신뢰도는 낮습니다.
- 이 `Func_uk_drivers_license` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 체크섬이 통과됩니다.

```xml
    <!-- U.K. Driver's License Number -->
    <Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75" relaxProximity="true" >
      <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_drivers_license" />
          <Match idRef="Keywords_eu_driver's_license_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_uk_drivers_license" />
        </Pattern>
    </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv 라이선스
- driv 라이선스
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl 번호


## <a name="uk-electoral-roll-number"></a>영국 선택 롤 번호

### <a name="format"></a>형식

2개의 문자와 1-4자리 숫자

### <a name="pattern"></a>패턴

2개의 문자(대소문자 구분 안 ), 1-4개 숫자

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
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


## <a name="uk-national-health-service-number"></a>영국 national health service number

### <a name="format"></a>형식

공백으로 구분된 10-17자리 숫자

### <a name="pattern"></a>패턴

10-17자리 숫자:
- 3자리 또는 10자리 숫자
- 공백
- 3자리 숫자
- 공백
- 4자리 숫자

### <a name="checksum"></a>체크섬

예

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
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

- GP
- DOB
- D.O.B
- Date of Birth
- Birth Date

## <a name="uk-national-insurance-number-nino"></a>영국 national insurance number (NINO)
이 중요한 정보 유형 엔터티는 EU 국가 식별 번호 중요한 정보 유형에 포함됩니다. 독립 실행형 중요한 정보 유형 엔터티로도 사용할 수 있습니다.

### <a name="format"></a>형식

공백 또는 대시로 구분된 7자 또는 9자

### <a name="pattern"></a>패턴

가능한 두 가지 패턴:

- 두 문자(유효한 NINOS는 이 연결의 유효성을 검사하는 특정 문자만 사용하고 대소문자는 구분하지 않습니다.)
- 6자리 숫자
- 'A', 'B', 'C' 또는 'D' 중 하나(접두사와 같이 접미사에는 특정 문자만 사용할 수 있습니다. 대소문자 구분 안 ).

또는

- 두 글자
- 공백 또는 대시
- 2자리 숫자
- 공백 또는 대시
- 2자리 숫자
- 공백 또는 대시
- 2자리 숫자
- 공백 또는 대시
- 'A', 'B', 'C' 또는 'D'

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- Func_uk_nino 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_uk_nino의 키워드가 발견되었습니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- Func_uk_nino 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.

```xml
    <!-- U.K. NINO -->
    <Entity id="16c07343-c26f-49d2-a987-3daf717e94cc" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nino" />
        <Match idRef="Keyword_uk_nino" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_nino" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_uk_nino"></a>Keyword_uk_nino

- national insurance number
- national insurance contributions
- protection act
- insurance
- social security number
- insurance application
- medical application
- social insurance
- medical attention
- social security
- great britain
- NI 번호
- NI 아니요.
- NI #
- NI #
- insurance #
- insurancenumber
- nationalinsurance #
- nationalinsurancenumber


## <a name="uk-unique-taxpayer-reference-number"></a>영국 고유 납세자 참조 번호

이 중요한 정보 유형은 다음에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거버넌스
- 레코드 관리
- Microsoft 클라우드 앱 보안

### <a name="format"></a>형식

공백 및 디지타이터가 없는 10자리 숫자


### <a name="pattern"></a>패턴

10자리 숫자

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 이  `Func_uk_eu_tax_file_number` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 시작  `Keywords_uk_eu_tax_file_number` 키워드가 발견됩니다.

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

- tax number
- tax file
- tax id
- tax identification no
- tax identification number
- tax no #
- tax no
- tax registration number
- 에 대한 나타 #
- 일자 #
- 일자 수 #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #

## <a name="us-bank-account-number"></a>미국 은행 계좌 번호

### <a name="format"></a>형식

6-17자리 숫자

### <a name="pattern"></a>패턴

6-17자리 연속 숫자

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
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

### <a name="format"></a>형식

주마다 다릅니다.

### <a name="pattern"></a>패턴

주에 따라 다를 수 있습니다. 예: 뉴욕:
- ddd ddd ddd와 같은 9자리 숫자가 일치합니다.
- dddddd와 같은 9자리 숫자는 일치하지 않습니다.

### <a name="checksum"></a>체크섬

아니요

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- Func_new_york_drivers_license_number 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_[state_name]_drivers_license_name의 키워드가 발견되었습니다.
- 검색된 Keyword_us_drivers_license 발견됩니다.

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있다는 신뢰도는 낮습니다.
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
- DLS
- CDL
- CDLS
- ID
- IDs
- DL #
- DLS #
- CDL #
- CDLS #
- ID #
- IDs #
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
- DriversLicense
- DriversLicenses
- Drivers Lic
- Drivers Lics
- Drivers License
- Drivers Licenses
- Driver'Lic
- Driver'Lics
- Driver'License
- Driver'Licenses
- Driver' Lic
- Driver' Lics
- Driver' License
- Driver' Licenses
- Driver'sLic
- Driver'sLics
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
- DriversLicense #
- DriversLicenses #
- Drivers Lic#
- Drivers Lics#
- Drivers License#
- Drivers Licenses#
- Driver'Lic #
- Driver'Lics #
- Driver'License #
- Driver'Licenses #
- Driver' Lic#
- Driver' Lics#
- Driver' License#
- Driver' Licenses#
- Driver'sLic #
- Driver'sLics #
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


#### <a name="keyword_state_name_drivers_license_name"></a>Keyword_[state_name]_drivers_license_name

- 상태 약어(예: "NY")
- 상태 이름(예: "New York")

## <a name="us-individual-taxpayer-identification-number-itin"></a>미국 ITIN(개인 납세자 번호)

### <a name="format"></a>형식

"9"로 시작하고 "7" 또는 "8"을 네 번째 숫자로 포함하는 9자리 숫자이며 선택적으로 공백 또는 대시로 서식이 지정됩니다.

### <a name="pattern"></a>패턴

서식 있는 형식:
- 숫자 "9"
- 2자리 숫자
- 공백 또는 대시
- "7" 또는 "8"
- 숫자
- 공백 또는 대시
- 4자리 숫자

unformatted:
- 숫자 "9"
- 2자리 숫자
- "7" 또는 "8"
- 5자리 숫자

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- Func_formatted_itin 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_itin의 키워드가 발견되었습니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- Func_unformatted_itin 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- Keyword_itin의 키워드가 발견되었습니다.

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있다는 신뢰도는 낮습니다.
- 이 Func_formatted_itin Func_unformatted_itin 일치하는 콘텐츠를 찾을 수 있습니다.

```xml
    <!-- U.S. Individual Taxpayer Identification Number (ITIN) -->
    <Entity id="e55e2a32-f92d-4985-a35d-a0b269eb687b" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_formatted_itin" />
        <Match idRef="Keyword_itin" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_itin" />
        <Match idRef="Keyword_itin" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_formatted_itin" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_unformatted_itin" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_itin"></a>Keyword_itin

- taxpayer
- tax id
- tax identification
- itin
- i.t.i.n.
- ssn
- tin
- social security
- tax payer
- itins
- 에 대한 나타
- individual taxpayer


## <a name="us-social-security-number-ssn"></a>미국 SSN(사회 보장 번호)

### <a name="format"></a>형식

서식이 지정되거나 서식 없는 패턴일 수 있는 9자리 숫자

> [!NOTE]
> 2011년 중반 전에 발급된 SSN의 서식은 강력합니다. 이 서식은 숫자의 특정 부분이 특정 범위 내에 있어야 합니다(체크 UM은 없음).

### <a name="pattern"></a>패턴

네 가지 함수는 네 가지 다른 패턴에서 SSNS를 찾아보세요.
- Func_ssn 대시 또는 공백으로 서식이 지정되어 있는 2011년보다 강력한 서식이 있는 SSNS를 검색합니다(ddd-dd-dd-dddd OR ddd dddd).
- Func_unformatted_ssn 9자리 연속 숫자로 서식이 지정되지 않은 강력한 2011 강력한 서식의 SSNS를 검색합니다(dddddddddd).
- Func_randomized_formatted_ssn 공백(ddd-dd-dddd OR ddd d)으로 서식이 지정된 2011년 후 SSNS를 검색합니다.
- Func_randomized_unformatted_ssn 9자리 연속 숫자로폼이 없는 2011년 후 SSNS를 검색합니다(dddddddd).

### <a name="checksum"></a>체크섬

아니오


### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- 이 `Func_ssn` 함수는 해당 패턴과 일치하는 콘텐츠를 검색합니다.
- 시작 `Keyword_ssn` 키워드가 발견됩니다.

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 함수가 Func_unformatted_ssn 일치하는 콘텐츠를 검색합니다.
- 시작 `Keyword_ssn` 키워드가 발견됩니다.

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있다는 신뢰도는 낮습니다.
- 함수가 `Func_randomized_formatted_ssn` `Func_randomized_unformatted_ssn` 해당 패턴과 일치하는 콘텐츠를 찾거나 검색합니다.
- 시작 `Keyword_ssn` 키워드가 발견됩니다.


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
- social security #
- social security #
- social security no
- Social Security#
- Soc Sec
- SSN
- SSNS
- SSN #
- SS #
- SSID

## <a name="us--uk-passport-number"></a>미국/영국 passport number

### <a name="format"></a>형식

9자리 숫자

### <a name="pattern"></a>패턴

- 한 문자 또는 숫자
- 8자리 숫자

### <a name="checksum"></a>체크섬

아니요

### <a name="definition"></a>정의

DLP 정책은 300자 이내의 근접성으로 이러한 유형의 중요한 정보를 검색할 수 있습니다.
- Func_usa_uk_passport 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- 키워드를 `Keywords_eu_passport_number` `Keywords_uk_eu_passport_number` 찾거나 찾은 경우
- 키워드를 `Keywords_eu_passport_date` 찾은 경우

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- Func_usa_uk_passport 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.
- 키워드를 `Keywords_eu_passport_number` `Keywords_uk_eu_passport_number` 찾거나 찾은 경우

```xml
    <!-- U.S. / U.K. Passport Number -->
    <Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
       <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_usa_uk_passport" />
          <Match idRef="Keywords_eu_passport_date" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_uk_eu_passport_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_usa_uk_passport" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_uk_eu_passport_number" />
          </Any>
        </Pattern>
    </Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_uk_eu_passport_number"></a>Keywords_uk_eu_passport_number

- british passport
- uk passport


## <a name="ukraine-passport-domestic"></a>우크라이나 여권 국내
이 중요한 정보 유형은 다음에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거버넌스
- 레코드 관리
- Microsoft 클라우드 앱 보안

### <a name="format"></a>형식

9자리 숫자

### <a name="pattern"></a>패턴

9자리 숫자

### <a name="checksum"></a>체크섬

아니오

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- regex Regex_Ukraine_Passport_Domestic 일치하는 콘텐츠를 검색합니다.
- 검색된 Keyword_Ukraine_Passport_Domestic 발견됩니다.

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
- passport number
- passport no
- паспорт України
- номер паспорта
- персональний


## <a name="ukraine-passport-international"></a>우크라이나 여권 국제
이 중요한 정보 유형은 다음에서만 사용할 수 있습니다.
- 데이터 손실 방지 정책
- 통신 준수 정책
- 정보 거버넌스
- 레코드 관리
- Microsoft 클라우드 앱 보안

### <a name="format"></a>형식

8자 영문 패턴

### <a name="pattern"></a>패턴

8자 영문 패턴:
- 2개의 문자 또는 숫자
- 6자리 숫자

### <a name="checksum"></a>체크섬

아니요

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- regex Regex_Ukraine_Passport_International 패턴과 일치하는 콘텐츠를 검색합니다.
- 검색된 Keyword_Ukraine_Passport_International 발견됩니다.

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
- passport number
- passport no
- паспорт України
- номер паспорта
