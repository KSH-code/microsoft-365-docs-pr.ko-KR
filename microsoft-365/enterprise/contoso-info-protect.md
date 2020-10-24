---
title: Contoso Corporation의 정보 보호
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/02/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso가 Microsoft 365의 정보 보호 기능을 사용 하 여 클라우드의 디지털 자산을 보호 하는 방법을 이해 합니다.
ms.openlocfilehash: a1aa08a20d284d3a003f4a406c37f2107ce19bd1
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754608"
---
# <a name="information-protection-for-the-contoso-corporation"></a>Contoso Corporation의 정보 보호

Contoso는 정보 보안에 대해 심각 합니다. 제품 디자인 및 독점 제조 기술을 설명 하는 지적 재산의 누출 또는 파괴로 인해 경쟁 우위에 배치 됩니다.

Contoso는 중요 한 디지털 자산을 클라우드로 이동 하기 전에 온-프레미스 정보 분류 및 보호 요구 사항이 회사의 Microsoft 365 클라우드 기반 서비스에서 지원 되는지 확인 했습니다.

## <a name="contoso-data-security-classification"></a>Contoso 데이터 보안 분류

Contoso는 데이터에 대 한 분석을 수행 하 고 다음과 같은 분류 수준을 결정 했습니다.

| 수준 1: 기본 데이터 | 수준 2: 중요 데이터 | 수준 3: 높은 규제 대상 데이터 |
|:-------|:-----|:-----|
| 데이터가 암호화되며 인증된 사용자에게만 제공됩니다.<BR> <BR> 온-프레미스와 클라우드 기반 저장소 및 작업 부하에 저장 된 모든 데이터에 대해 제공 됩니다. 데이터는 서비스에 상주 하 고 서비스와 클라이언트 장치 간에 전송 되는 동안 암호화 됩니다. <BR><BR>수준 1 데이터의 예로는 관리/영업/지원 담당자의 파일 및 일반적인 업무 관련 통신 내용(전자 메일)이 있습니다. | 수준 1의 기능과 함께 높은 수준의 인증 및 데이터 손실 방지 기능을 제공합니다.<BR> <BR> 강력한 인증에는 SMS 유효성 검사와 함께 Azure MFA(다단계 인증)를 포함합니다. 데이터 손실 방지는 중요 한 정보 또는 중요 한 정보가 Microsoft 클라우드 외부로 이동 하지 않도록 합니다.<BR><BR>수준 2 데이터의 예로는 신제품 연구 개발 데이터 및 재무/법률 정보가 있습니다. | 수준 2의 기능과 함께 최고 수준의 암호화, 인증 및 감사 기능 제공<BR><BR>미사용 데이터 및 클라우드의 데이터에 대해 지역별 규정을 준수하는 최고 수준의 암호화 기능이 제공되며, 스마트 카드를 사용하는 MFA와 세분화된 감사/경고 기능도 함께 제공됩니다.<BR> <BR>수준 3 데이터의 예로는 고객 및 파트너 개인 정보, 제품 엔지니어링 사양 및 독점 제조 기술이 있습니다.  |
||||

## <a name="contoso-information-policies"></a>Contoso 정보 정책
다음 표에는 Contoso 정보 정책이 나와 있습니다.


| 값 | Access | 데이터 보존 | 정보 보호 |
|:-------|:-----|:-----|:-----|
| 비즈니스 가치가 낮은 데이터(수준 1: 기본 데이터) | 모든 권한을 허용 합니다.  | 6개월 | 암호화 사용. |
| 비즈니스 가치가 중간 정도인 데이터(수준 2: 중요 데이터) | Contoso 직원, 하도급 업자 및 파트너에 대 한 액세스를 허용 합니다. <BR><BR> MFA, TLS(전송 계층 보안) 및 MAM(모바일 응용 프로그램 관리) 사용. | 2년  | 데이터 무결성을 위해 해시 값 사용.  |
| 비즈니스 가치가 높은 데이터(수준 3: 높은 규제 대상 데이터) | 엔지니어링/제조 부문 임원과 책임자에 대해 액세스 허용. <BR> <BR> 관리되는 네트워크 장치만 있는 RMS(권한 관리 시스템).  | 7년  | 거부 없음이 설정된 디지털 서명 사용.  |
|||||

## <a name="the-contoso-path-to-information-protection-with-microsoft-365-for-enterprise"></a>엔터프라이즈에 대 한 Microsoft 365을 사용한 정보 보호를 위한 Contoso 경로

Contoso는 다음 단계를 수행 하 여 정보 보호 요구 사항에 대해 Microsoft 365 for enterprise를 준비 합니다.

1. 보호할 정보 식별

   Contoso는 온-프레미스 SharePoint 사이트 및 파일 공유에 있는 기존의 디지털 자산을 광범위 하 게 검토 했으며 각 자산을 분류 했습니다.

2. 데이터 수준에 대 한 액세스, 보존 및 정보 보호 정책 결정

   Contoso는 데이터 수준에 따라, 자세한 정책 요구 사항을 결정했습니다. 이러한 요구 사항은 기존 디지털 자산이 클라우드로 전환될 때 보호하는 데 사용되었습니다.

3. 다양 한 정보 수준에 대 한 민감도 레이블 및 설정 만들기

   Contoso는 암호화, 사용 권한 및 워터마크를 포함하여 높은 규제 대상 레이블을 사용하여 데이터 수준에 맞게 민감도 레이블을 만들었습니다.

4.  온-프레미스 SharePoint 사이트 및 파일 공유의 데이터를 새 SharePoint 사이트로 이동

    새 SharePoint 사이트로 마이그레이션된 파일에는 해당 사이트에 할당된 기본 보존 레이블이 상속되었습니다.

5.  직원 교육 새 문서에 민감도 레이블을 사용 하는 방법, 새 SharePoint 사이트를 만들 때 Contoso IT 그룹과 상호 작용 하는 방법 및 SharePoint 사이트에 항상 디지털 자산을 저장 하는 방법

    잘못 된 작업자 정보를 변경 하는 것은 일반적으로 클라우드의 정보 보호 전환에서 가장 어려운 부분으로 간주 됩니다. Contoso IT 및 관리 직원은 항상 클라우드에서 디지털 자산을 레이블을 지정 및 저장 하 고, 온-프레미스 파일 공유를 사용 하지 않고, 타사 클라우드 저장소 서비스 또는 USB 드라이브를 사용 하지 않도록 하는 데 필요 합니다.

## <a name="conditional-access-policies-for-information-protection"></a>정보 보호에 대한 조건부 액세스 정책

Exchange Online 및 SharePoint 배포의 일환으로 Contoso는 다음과 같은 조건부 액세스 정책 집합을 구성 하 고 해당 그룹에 적용 했습니다.

- [장치 정책에 대한 관리 및 비관리 응용 프로그램 액세스](../security/office-365-security/identity-access-policies.md)
- [Exchange Online 액세스 정책](../security/office-365-security/secure-email-recommended-policies.md)
- [SharePoint 액세스 정책](../security/office-365-security/sharepoint-file-access-policies.md)

정보 보호에 대 한 Contoso 정책의 결과 집합은 다음과 같습니다.

![장치, Exchange Online 및 SharePoint 조건부 액세스 정책](../media/contoso-info-protect/contoso-info-protect-fig1.png)

>[!Note]
>또한 Contoso는 ID 및 로그인에 대한 조건부 액세스 정책을 추가로 구성했습니다. [Contoso Corporation ID](contoso-identity.md#conditional-access-policies-for-identity-and-device-access)를 참조하세요.
>

이러한 정책은 다음을 보장합니다.

- 허용 되는 앱 및 조직의 데이터로 수행할 수 있는 작업은 앱 보호 정책에 의해 정의 됩니다.
- PC 및 모바일 장치는 규격이어야 합니다.
- Exchange Online은 Exchange Online에 Office 365 메시지 암호화 (OME)를 사용 합니다.
- SharePoint에서는 앱 적용 제한을 사용 합니다.
- SharePoint는 브라우저 전용 액세스에 대해 액세스 제어 정책을 사용하고 관리되지 않는 장치에 대한 액세스를 차단합니다.

## <a name="mapping-microsoft-365-for-enterprise-features-to-contoso-data-levels"></a>Microsoft 365 for enterprise 기능을 Contoso 데이터 수준으로 매핑

다음 표에는 Contoso 데이터 수준이 기업에 대 한 Microsoft 365의 정보 보호 기능에 매핑됩니다.

| 수준 | Microsoft 365 클라우드 서비스 | Windows 10 및 Microsoft Office 365 ProPlus | 보안 및 규정 준수 |
|:-------|:-----|:-----|:-----|
| 수준 1: 기본 데이터  | SharePoint 및 Exchange Online 조건부 액세스 정책 <BR> SharePoint 사이트에 대한 권한 | 민감도 레이블 <BR> BitLocker <BR> Windows Information Protection | 장치 조건부 액세스 정책 및 모바일 응용 프로그램 관리 정책 |
| 수준 2: 중요 데이터 | 수준 1 추가: <BR> <BR> 민감도 레이블 <BR> SharePoint 사이트의 Microsoft 365 보존 레이블 <BR> SharePoint Online 및 Exchange Online용 데이터 손실 방지 <BR> 격리된 SharePoint 사이트  | 수준 1 추가: <BR> <BR> 디지털 자산의 민감도 레이블  | 수준 1 |
| 수준 3: 높은 규제 대상 데이터 | 수준 2 추가: <BR><BR> 거래 비밀 정보에 대 한 사용자 키 (BYOK) 암호화 및 보호 <BR> Microsoft 365 서비스와 상호 작용 하는 기간 업무 (lob) 응용 프로그램에 대 한 Azure Key Vault | 수준 2 | 수준 1 |
|||||

다음은 Contoso information protection 구성의 결과입니다.

![Contoso의 결과 정보 보호 구성](../media/contoso-info-protect/contoso-info-protect-fig2.png)

## <a name="next-step"></a>다음 단계

Contoso에서 id 및 액세스 관리, 위협 방지, 정보 보호 및 보안 관리를 위해 [Microsoft 365의 보안 기능](contoso-security-summary.md) 을 사용 하는 방법을 알아봅니다.

## <a name="see-also"></a>참고 항목

[보안 로드맵](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap)

[엔터프라이즈용 Microsoft 365 개요](microsoft-365-overview.md)

[테스트 랩 가이드](m365-enterprise-test-lab-guides.md)
