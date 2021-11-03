---
title: 데이터 손실 방지 정책 팁 참조
f1.keywords: CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- SPO160
- MET150
ms.assetid: 6501b5ef-6bf7-43df-b60d-f65781847d6c
ms.collection:
- M365-security-compliance
- SPO_Content
recommendations: false
description: DLP(데이터 손실 방지) 정책에 정책 팁을 추가하여 사용자에게 DLP 정책과 충돌하는 콘텐츠를 사용 중일 때 이를 알리는 방법을 알아보겠습니다.
ms.custom: seo-marvel-apr2021
ms.openlocfilehash: f4aeefca80412c225da1b2f589d109355be21305
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2021
ms.locfileid: "60701986"
---
# <a name="data-loss-prevention-policy-tips-reference"></a>데이터 손실 방지 정책 팁 참조

Outlook Web Access의 DLP 정책 팁은 다음을 제외한 DLP 정책의 Exchange 작업에 적용되는 모든 조건, 예외 및 작업에 대해 지원됩니다.

**조건:**

- 보낸 사람 Is
- 보낸 사람 도메인
- 받는 사람이 다음의 구성원임
- 헤더에 단어 또는 구가 포함되어 있습니다.
- 헤더가 패턴과 일치
- 문서 크기가 같거나 보다 크거나 같은 경우
- 메시지 유형은
- 메시지 중요도
- 콘텐츠 문자 집합에 단어 포함
- 제목 또는 본문에 단어 또는 구가 포함되어 있습니다.
- 제목 또는 본문이 패턴과 일치
- 콘텐츠 문자 집합에 단어 포함
- 콘텐츠 수신
- 보낸 사람이 정책 팁을 다시 정해 두었기
- 메시지 크기가 같거나 보다 크기
- 보낸 사람 AD 특성에 단어 또는 구가 포함되어 있습니다.
- 보낸 사람 AD 특성이 패턴 일치
- 문서 콘텐츠에 단어 또는 구가 포함되어 있습니다.
- 문서 콘텐츠 일치 패턴

**작업:**

- 승인을 위해 보낸 사람 관리자에게 메시지 전달
- 특정 승인자에 대한 승인을 위해 메시지 전달
- 메시지를 특정 사용자로 리디렉션
- 받는 사람 상자에 받는 사람 추가
- Cc Box에 받는 사람 추가
- Bcc Box에 받는 사람 추가
- 보낸 사람의 관리자를 받는 사람으로 추가
- HTML 고지 조항 추가
- 전자 메일 제목 추가
- O365 메시지 암호화 및 권한 보호 제거

## <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions"></a>Outlook 2013 이상에서는 일부 조건 및 예외에 대한 정책 팁 표시 지원

현재 Outlook 2013 이상에서는 아래 언급된 조건 및 해당 예외와 별도로 조건이나 예외를 포함하지 않는 정책에 대한 정책 팁 표시를 지원하고 있습니다.

- 콘텐츠 포함(중요한 정보 유형에만 해당) 민감도 레이블이 지원되지 않습니다.
- 콘텐츠 공유

모든 조건은 Outlook 클라이언트 앱에서 작성된 전자 메일에 대해 작동하며, 콘텐츠와 일치하고 콘텐츠에 보호 작업을 적용합니다. 그러나 사용자에게 정책 팁을 표시하는 것은 위에서 언급한 조건과는 별도로 사용되는 조건에 대해 지원되지 않습니다.

## <a name="outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types"></a>Outlook 2013 이상 및 Office 데스크톱의 앱 지원에는 일부 중요한 정보 유형에 대한 정책 팁만 표시

데스크톱의 Outlook(2013 이상) 및 데스크톱의 Office 앱(Word, Excel, PowerPoint)에 DLP 정책 팁을 표시하기 위해 검색될 예정인 바로 중요한 정보 유형 목록은 다음과 같습니다.

- ABA 라우팅 번호
- 아르헨티나 국가 ID(DNI) 번호
- 호주 은행 계좌 번호
- 호주 의료 계좌 번호
- 호주 여권 번호
- 호주 세금 파일 번호
- Azure DocumentDB Auth 키  
- Azure IAAS 데이터베이스 연결 문자열 및 Azure SQL 연결 문자열  
- Azure IoT 연결 문자열  
- Azure 게시 설정 암호  
- Azure Redis 캐시 연결 문자열  
- Azure SAS  
- Azure Service Bus 연결 문자열  
- Azure Storage 계정 키  
- Azure Storage 계정 키(일반)  
- 벨기에 국가 번호
- 브라질 CPF 번호
- 브라질 법인 번호(CNPJ)
- 	브라질 국가 ID 카드(RG)
- 캐나다 은행 계좌 번호
- 캐나다 운전 면허 번호
- 캐나다 건강 서비스 번호
- 캐나다 여권 번호
- 캐나다 PHIN(개인 건강 식별 번호)
- 캐나다 사회 보험 번호
- 	칠레 ID 카드 번호
- 	중국 주민 ID 카드(PRC) 번호
- 신용 카드 번호
- 크로아티아 ID 카드 번호  
- 크로아티아 개인 식별(OIB) 번호  
- 체코 개인 ID 번호  
- 덴마크 개인 식별 번호
- DEA(약물 집행 기구) 번호
- 유럽 직불 카드 번호
- EU 운전 면허 번호  
- EU 국가 식별 번호  
- EU 여권 번호  
- EU SSN(사회 보장 번호) 또는 동등한 ID  
- EU 세금 식별 번호(TIN)  
- 핀란드 국가 ID
- 핀란드 여권 번호
- 프랑스 운전 면허 번호
- 프랑스 국가 ID 카드(CNI)
- 프랑스 여권 번호
- 프랑스 사회 보장 번호(INSEE)
- 독일 운전 면허 번호
- 독일 여권 번호
- 독일 ID 카드 번호
- 그리스 국가 ID 카드  
- HKID(홍콩 ID 카드) 번호
- 인도 PAN(영구 계정 번호)
- 인도 고유 ID(Aadhaar) 번호
- 인도네시아 ID 카드(KTP) 번호
- IBAN(국제 은행 계좌 번호)
- 국제질병 분류(ICD-10-CM)  
- 국제질병 분류(ICD-9-CM)  
- IP 주소
- 아일랜드 PPS(개인 공공 서비스) 번호 
- 이스라엘 은행 계좌 번호
- 이스라엘 국가 ID
- 이탈리아 운전 면허 번호
- 일본 은행 계좌 번호
- 일본 운전 면허 번호
- 일본 여권 번호
- 일본 주민 등록 번호
- 일본 SIN(사회 보험 번호)
- 일본어 거주 카드 번호
- 말레이시아 ID 카드 번호
- 네덜란드 시민 서비스(BSN) 번호  
- 뉴질랜드 보건부 번호
- 노르웨이 ID 번호  
- 필리핀 통합 다목적 ID 번호
- 폴란드 ID 카드
- 폴란드 국가 ID(PESEL)
- 폴란드 여권
- 포르투갈 시민 카드 번호
- 사우디 아라비아 국가 ID
- 싱가포르 NRIC(국가 등록 ID 카드) 번호
- 남아프리카 공화국 식별 번호  
- 한국 주민 등록 번호
- 스페인 SSN(사회 보장 번호)
- SQL Server 연결 문자열  
- 스웨덴 국가 ID
- 스웨덴 여권 번호
- SWIFT 코드
- 대만 국가 ID
- 	대만 여권 번호
- 대만 거주 인증서(ARC/TARC)
- 태국어 인구 식별 코드
- 터키어 국가 ID 번호
- 영국 운전 면허 번호
- 영국 선거 롤 번호
- 영국 국립 보건 서비스 번호
- 영국 NINO(국민 보험 번호)
- 미국/영국 여권 번호
- 미국 은행 계좌 번호
- 미국 운전 면허 번호
- 미국 ITIN(개인 납세자 번호)
- 미국 SSN(사회 보험 번호)

사용자 지정 중요한 정보 유형은 위의 중요한 정보 유형 외에 DLP 정책 팁에도 지원됩니다.

## <a name="data-loss-prevention-on-endpoint-devices-supports-policy-tips-for-only-some-sensitive-information-types"></a>끝점 장치의 데이터 손실 방지는 일부 중요한 정보 유형에 대한 정책 팁만 지원합니다.

끝점 장치에 있는 문서에서 검색되는 바로 사용 가능한 중요한 정보 유형 목록은 다음과 같습니다.

- ABA 라우팅 번호 
- 아르헨티나 국가 ID(DNI) 번호 
- 호주 은행 계좌 번호 
- 호주 의료 계좌 번호 
- 호주 여권 번호 
- 호주 세금 파일 번호 
- 오스트레일리아 비즈니스 번호 
- 오스트레일리아 회사 번호 
- 오스트리아 운전 면허 번호 
- 오스트리아 ID 카드 
- 오스트리아 여권 번호 
- 오스트리아 사회 보장 번호 
- 오스트리아 세금 식별 번호 
- 오스트리아 부가가치세(VAT) 번호 
- Azure DocumentDB Auth 키 
- Azure IAAS 데이터베이스 연결 문자열 및 Azure SQL 연결 문자열 
- Azure IoT 연결 문자열 
- Azure 게시 설정 암호 
- Azure Redis 캐시 연결 문자열 
- Azure SAS 
- Azure Service Bus 연결 문자열 
- Azure Storage 계정 키 
- Azure Storage 계정 키(일반) 
- 벨기에 운전 면허 번호 
- 벨기에 국가 번호 
- 벨기에 여권 번호 
- 벨기에 부가가치세 번호 
- 브라질 CPF 번호 
- 브라질 법인 번호(CNPJ) 
- 	브라질 국가 ID 카드(RG) 
- 불가리아 운전 면허 번호 
- 불가리아 여권 번호 
- 불가리아 제복민 번호 
- 캐나다 은행 계좌 번호 
- 캐나다 운전 면허 번호 
- 캐나다 건강 서비스 번호 
- 캐나다 여권 번호 
- 캐나다 PHIN(개인 건강 식별 번호) 
- 캐나다 사회 보험 번호 
- 	칠레 ID 카드 번호 
- 	중국 주민 ID 카드(PRC) 번호 
- 신용 카드 번호 
- 크로아티아 운전 면허 번호 
- 크로아티아 ID 카드 번호 
- 크로아티아 국가 ID 카드 번호 
- 크로아티아 여권 번호 
- 크로아티아 개인 식별(OIB) 번호 
- CSCAN-AZURE0060 Azure Storage 계정 공유 액세스 서명 
- CSCAN-GENERAL0140 일반 대칭 키 
- 키프로스 드라이버의 라이선스 번호 
- 키프로스 ID 카드 
- 키프로스 여권 번호 
- 키프로스 세금 식별 번호 
- 체코 운전 면허 번호 
- 체코 개인 ID 번호 
- 체코 여권 번호 
- 덴마크 운전 면허 번호 
- 덴마크 여권 번호 
- 덴마크 개인 식별 번호 
- DEA(약물 집행 기구) 번호 
- 에스토니아 운전 면허 번호 
- 에스토니아 여권 번호 
- 에스토니아 개인 식별 코드 
- 유럽 직불 카드 번호 
- EU 운전 면허 번호 
- EU 국가 식별 번호 
- EU 여권 번호 
- EU SSN(사회 보장 번호) 또는 동등한 ID 
- EU 세금 식별 번호(TIN) 
- 핀란드 운전 면허 번호 
- 핀란드 유럽 보건 보험 번호 
- 핀란드 국가 ID 
- 핀란드 여권 번호 
- 프랑스 운전 면허 번호 
- 프랑스 건강 보험 번호 
- 프랑스 국가 ID 카드(CNI) 
- 프랑스 여권 번호 
- 프랑스 사회 보장 번호(INSEE) 
- 프랑스 세금 식별 번호(numéro SPI.) 
- 프랑스 부가가치세 번호 
- 독일 운전 면허 번호 
- 독일 여권 번호 
- 독일 ID 카드 번호 
- 독일 세금 식별 번호 
- 독일 부가가치세 번호 
- 그리스 운전 면허 번호 
- 그리스 국가 ID 카드 
- 그리스 여권 번호 
- 그리스 AMKA(사회 보장 번호) 
- 그리스어 세금 식별 번호 
- HKID(홍콩 ID 카드) 번호 
- TAJ(헝가리어 사회 보장 번호) 
- 헝가리어 부가가치세 번호 
- 헝가리 운전 면허 번호 
- 헝가리 여권 번호 
- 헝가리 개인 식별 번호 
- 헝가리 세금 식별 번호 
- 인도 PAN(영구 계정 번호) 
- 인도 고유 ID(Aadhaar) 번호 
- 인도네시아 ID 카드(KTP) 번호 
- IBAN(국제 은행 계좌 번호) 
- 국제질병 분류(ICD-10-CM) 
- 국제질병 분류(ICD-9-CM) 
- IP 주소 
- 아일랜드 운전 면허 번호 
- 아일랜드 여권 번호 
- 아일랜드 PPS(개인 공공 서비스) 번호 
- 이스라엘 은행 계좌 번호 
- 이스라엘 국가 ID 
- 이탈리아 운전 면허 번호 
- 이탈리아 회계 코드 
- 이탈리아 여권 번호 
- 이탈리아 부가가치세 번호 
- 일본 은행 계좌 번호 
- 일본 운전 면허 번호 
- 일본 여권 번호 
- 일본 주민 등록 번호 
- 일본 SIN(사회 보험 번호) 
- 일본어 마이 번호 회사 
- 일본어 마이 번호 개인 
- 일본어 거주 카드 번호 
- 라트비아 운전 면허 번호 
- 라트비아 여권 번호 
- 라트비아 개인 코드 
- 리투아니아 운전 면허 번호 
- 리투아니아 여권 번호 
- 리투아니아 개인 코드 
- 룩세르버그 운전 면허 번호 
- 룩룩부르크 국가 식별 번호(자연인) 
- 룩세르버그 국가 식별 번호(자연인이 아닌 사람) 
- 룩세르버그 여권 번호 
- 말레이시아 ID 카드 번호 
- 몰타 운전 면허 번호 
- 몰타 ID 카드 번호 
- 몰타 여권 번호 
- 몰타 세금 ID 번호 
- 네덜란드 시민 서비스(BSN) 번호 
- 네덜란드 운전 면허 번호 
- 네덜란드 여권 번호 
- 네덜란드 세금 식별 번호 
- 네덜란드 부가가치세 번호 
- 뉴질랜드 은행 계좌 번호 
- 뉴질랜드 운전 면허 번호 
- 뉴질랜드 내륙 수익 번호 
- 뉴질랜드 보건부 번호 
- 뉴질랜드 사회 일지 번호 
- 노르웨이 ID 번호 
- 필리핀 통합 다목적 ID 번호 
- 폴란드 운전 면허 번호 
- 폴란드 ID 카드 
- 폴란드 국가 ID(PESEL) 
- 폴란드 여권 
- 폴란드 세금 식별 번호 
- 폴란드어 REGON 번호 
- 포르투갈 시민 카드 번호 
- 포르투갈 운전 면허 번호 
- 포르투갈 여권 번호 
- 포르투갈 세금 식별 번호 
- 루마니아 운전 면허 번호 
- 루마니아 여권 번호 
- 루마니아 CNP(개인 번호 코드) 
- 러시아 여권 번호(국내) 
- 러시아 여권 번호(국제) 
- 사우디 아라비아 국가 ID 
- 싱가포르 NRIC(국가 등록 ID 카드) 번호 
- 슬로바키아 운전 면허 번호 
- 슬로바키아 여권 번호 
- 슬로바키아 개인 번호 
- Slovenia Driver's License Number 
- Slovenia Passport Number 
- 솔로베니아 세금 식별 번호 
- Slovenia Unique Master Citizen Number 
- 남아프리카 공화국 식별 번호 
- 한국 주민 등록 번호 
- 스페인 DNI 
- 스페인 운전 면허 번호 
- 스페인 여권 번호 
- 스페인 SSN(사회 보장 번호) 
- 스페인 세금 식별 번호 
- SQL Server 연결 문자열 
- 스웨덴 운전 면허 번호 
- 스웨덴 국가 ID 
- 스웨덴 여권 번호 
- 스웨덴 세금 식별 번호 
- SWIFT 코드 
- Swiss Social Security Number AHV 
- 대만 국가 ID 
- 	대만 여권 번호 
- 대만 거주 인증서(ARC/TARC) 
- 태국어 인구 식별 코드 
- 터키어 국가 ID 번호 
- 영국 운전 면허 번호 
- 영국 선거 롤 번호 
- 영국 국립 보건 서비스 번호 
- 영국 NINO(국민 보험 번호) 
- 영국 고유 납세자 참조 번호 
- 미국/영국 여권 번호 
- 미국 은행 계좌 번호 
- 미국 운전 면허 번호 
- 미국 ITIN(개인 납세자 번호) 
- 미국 SSN(사회 보험 번호) 
- 우크라이나 여권 번호(국내) 
- 우크라이나 여권 번호(국제) 
 
사용자 지정 중요한 정보 유형은 위에 설명된 중요한 정보 유형 외에도 검색됩니다.

## <a name="support-matrix-for-dlp-policy-tips-across-microsoft-apps"></a>Microsoft 앱의 DLP 정책 팁 지원 매트릭스

|**앱 및 플랫폼**|**DLP 정책 팁 지원**|**지원되는 중요한 정보 유형**|**지원되는 사전 및 작업**|**Comments**|
|:--|:--|:--|:--|:--|
|**Outlook 웹에서**|:::image type="icon" source="../media/rightmrk.png" border="false":::|all|하위 집합||
|**Outlook Win32(ver. 2105 빌드 14026.20000 및 반기 채널 ver. 2102 빌드 13801.20862)**|:::image type="icon" source="../media/rightmrk.png" border="false":::|all|하위 집합|Outlook [2013](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions) 이상에서는 일부 조건 및 예외에 대한 정책 팁만 표시하고 [Outlook 2013](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types) 이상 및 데스크톱의 Office 앱 지원 지원에서는 중요한 정보 유형 및 DLP 조건에 대한 지원에 대한 자세한 내용과 Outlook Win32에 대한 DLP 정책 팁을 표시하는 데 지원되는 작업에 대한 일부 중요한 정보 유형에 대한 정책 팁만 보여 주실 수 있습니다. .|
|**Outlook 모바일(iOS, Android)/Outlook Mac**|:::image type="icon" source="../media/crsmrk.png" border="false":::|없음|없음|DLP 정책 팁은 모바일에서 Outlook 지원되지 않습니다.|
|**SharePoint 온라인/비즈니스용 OneDrive 웹 클라이언트**|:::image type="icon" source="../media/rightmrk.png" border="false":::|all|DLP의 모든 SPO/ODB 프레디트 및 작업||
|**SharePoint Win32/ 비즈니스용 OneDrive Win32 클라이언트**|:::image type="icon" source="../media/crsmrk.png" border="false":::|없음|없음|DLP 정책 팁은 데스크톱 클라이언트 SharePoint OneDrive 지원되지 않습니다.|
|**Word, Excel, PowerPoint 웹 클라이언트**|:::image type="icon" source="../media/rightmrk.png" border="false":::|all|DLP의 모든 SPO/ODB 프레디트 및 작업|문서가 SPO 또는 ODB 웹앱에 호스트되어 있으며 DLP 정책이 이미 스탬프 처리된 경우 DLP 정책 팁이 지원됩니다.|
|**Word, Excel, PowerPoint Mobile 클라이언트**|:::image type="icon" source="../media/crsmrk.png" border="false":::|없음|없음|DLP 정책 팁은 모바일 앱에 지원되지 Office.|
|**Teams Web/Teams Desktop/Teams Mobile/Teams Mac**|:::image type="icon" source="../media/rightmrk.png" border="false":::|all|모든 Teams DLP 정책의 모든 Teams|정책 팁은 메시지가 "이 메시지에 플래그가 지정된 경우 표시됩니다. 어떻게 해야 나요?" 링크를 클릭할 때 사용자는 감지된 중요한 정보 유형을 검토하고 관리자가 허용하는 경우 문제를 재지정하거나 보고할 수 있습니다. 파일에 대한 정책 팁은 표시하지 않습니다. 받는 사람이 문서에 액세스하는 경우 허용되지 않는 경우 액세스가 거부될 수 있습니다.|
|**Win32 끝점 장치**|:::image type="icon" source="../media/rightmrk.png" border="false":::|하위 집합|DLP 정책의 모든 끝점 DLP 사문자 및 작업|일부 중요한 정보 유형에 대한 정책 팁 지원 끝점의 데이터 손실 [방지를 참조하세요.](#data-loss-prevention-on-endpoint-devices-supports-policy-tips-for-only-some-sensitive-information-types)|
|**macOS 장치(미리 보기)**|기본 팁만|all|하위 집합|데이터 손실 방지 정책은 macOS 장치에서 적용할 수 있습니다. 사용자 지정 정책 팁은 지원되지 않습니다.|
|**제3자 클라우드 앱**|:::image type="icon" source="../media/crsmrk.png" border="false":::|없음|없음|데이터 손실 방지 정책 팁은 제3자 클라우드 앱에서 지원되지 않습니다.|
|**On-prem**|:::image type="icon" source="../media/crsmrk.png" border="false":::|없음|없음||
|**Word, Excel, PowerPoint Win32 Client**|:::image type="icon" source="../media/crsmrk.png" border="false":::|하위 집합|하위 집합|지원되는 중요한 정보 유형 목록에 대한 일부 중요한 정보 유형에 대한 정책 팁만 보여 Outlook [2013](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types) 이상 및 데스크톱의 Office 앱을 참조하세요.</br></br>WXP 클라이언트 앱에 대한 정책 팁은 SharePoint Online 또는 비즈니스용 OneDrive 사이트에 저장된 문서에서 DLP 정책의 조건 또는 작업 중 아래 또는 일부가 있는 모든 DLP 정책에 대해 작동됩니다.</br> <ul><li>콘텐츠에 중요한 정보 유형 포함</li><li>액세스 범위(콘텐츠가 내부/외부적으로 공유)</li><li>사용자에게 알림(정책 팁/사용자 알림)</li><li>모든 사람 차단</li><li>문제 보고서</li></ul></br> 다른 조건이나 작업이 있는 경우 해당 정책에 대한 DLP 정책 팁이 Word, Excel 또는 PowerPoint.</br>자세한 내용은 Excel, PowerPoint [및 Word의](use-notifications-and-policy-tips.md#policy-tips-in-excel-powerpoint-and-word) 정책 팁을 참조하세요.|
||||||
