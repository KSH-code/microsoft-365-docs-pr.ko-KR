---
title: Contoso IT 인프라 및 비즈니스 요구
author: kelleyvice-msft
f1.keywords:
- NOCSH
ms.author: kvice
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso 사내 IT 인프라의 기본 구조와 엔터프라이즈용 클라우드를 통해 회사의 비즈니스 요구를 Microsoft 365 이해합니다.
ms.openlocfilehash: aa0779cfadb12aa0213a74f2e348951be4eca4f5
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59218685"
---
# <a name="contoso-it-infrastructure-and-business-needs"></a>Contoso IT 인프라 및 비즈니스 요구

Contoso는 중앙 집중식 사내 IT 인프라에서 클라우드 기반 개인 생산성 워크로드 및 응용 프로그램을 통합하는 클라우드 포함 설치로 전환하고 있습니다.

## <a name="existing-contoso-it-infrastructure"></a>기존 Contoso IT 인프라

Contoso는 주로 중앙 집중식 온-프레미스 IT 인프라를 사용하며, 응용 프로그램 데이터 센터는 파리 본사에 있습니다.

다음은 응용 프로그램 데이터 센터, DMZ 및 인터넷이 있는 본사입니다.

![기존 Contoso IT 인프라.](../media/contoso-infra-needs/contoso-infra-needs-fig1.png)

온-프레미스 응용 프로그램 데이터 센터에서는 다음과 같은 것들을 호스팅합니다. 

- 응용 프로그램 및 기타 Linux 데이터베이스를 SQL Server 사용자 지정 업무(LINE-OF-BUSINESS) 응용 프로그램
- 레거시 SharePoint 서버 집합
- 파일 저장을 위한 조직 및 팀 수준 서버

또한 각 지역 허브 사무소는 유사한 응용 프로그램 집합을 가진 서버 집합을 지원합니다. 이 서버들은 지역 IT부서의 통제를 받습니다.

이러한 별도의 다중 지역 데이터 센터에 있는 응용 프로그램 및 데이터에 대한 검색 가능성은 계속해서 해결 과제로 남아 있습니다.

Contoso 본사 DMZ에서는 여러 서버 집합이 다음을 제공합니다.

- 고객이 제품, 파트, 소모품 및 서비스를 주문할 수 있는 Contoso 공용 웹 사이트에 대한 호스팅
- 파트너와의 정보 교환 및 공동 작업을 위한 Contoso 파트너 엑스트라넷 호스팅 기능
- 파리 본사 직원을 위한 Contoso 인트라넷 및 웹 프록시에 대한 VPN (가상 사설망) 기반 원격 액세스 기능

## <a name="contoso-business-needs"></a>Contoso 비즈니스 요구

Contoso 비즈니스 요구는 다음과 같은 다섯 가지 주요 범주로 분류됩니다.

**생산성**

- 보다 쉽게 공동으로 작업

  전자 메일 및 파일 공유 기반 공동 작업을 문서에 대한 실시간 변경, 보다 쉬운 온라인 모임 및 캡처된 대화 스레드를 허용하는 온라인 모델로 대체합니다.
- 원격 및 모바일 작업자의 생산성 향상

  많은 직원이 재택 근무 또는 현장에서 작업하는 경우 병목 현상이 있는 VPN 솔루션을 클라우드의 Contoso 데이터 및 리소스에 대한 다양한 액세스로 대체하세요.
- 창의성 및 혁신 증대

  수동 입력과 3D 시각화를 포함하여 최신 수준의 시각적 학습 및 아이디어 개발 방식을 활용할 수 있습니다.


**보안**

- ID 및 액세스 관리

  다단계 및 기타 인증 형식을 적용하고 사용자 및 관리자 계정 자격 증명을 보호합니다.

- 위협 방지

  맬웨어를 포함하는 외부 보안 위협으로부터 보호 -> 맬웨어를 포함하여 외부 보안 위협으로부터 보호

- 정보 보호

  고객 데이터, 디자인 및 제조 사양 및 직원 정보와 같은 고가치 디지털 자산에 대한 액세스를 잠그고 암호화합니다.

- 보안 관리

  보안 자세를 모니터링하고 위협을 실시간으로 감지하고 대응합니다.

**원격 및 모바일 액세스 및 비즈니스 파트너**

- 원격 및 모바일 작업자의 보안 향상

  BYOD(Bring Your Own Device) 및 회사 소유의 장치 관리를 구현하여 보안 액세스, 올바른 응용 프로그램 동작 및 회사 데이터 보호를 보장합니다.

- 직원을 위한 원격 액세스 인프라 감소

  일반적으로 액세스하는 리소스를 클라우드로 이동하여 유지 관리 및 지원 비용을 절감하고 원격 액세스 솔루션의 성능을 향상합니다.

- B2B(비즈니스 대 Susiness) 트랜잭션에 대한 연결 향상 및 오버헤드 감소

  페더넷 인증을 사용하는 클라우드 기반 솔루션으로 고가의 고가의 파트너 엑스트라넷을 대체합니다.

**규정 준수**

- 지역별 규정 준수

  데이터 저장, 암호화, 데이터 개인 정보 보호 및 유럽 연합에 대한 GDPR(일반 데이터 보호 규정)과 같은 개인 데이터 규정에 대한 산업 및 지역 규정을 준수합니다.

**관리**

- 클라이언트 PC 및 장치에서 실행되는 소프트웨어를 관리하기 위한 IT 오버헤드 감소

  조직 전체에서 Windows 및 엔터프라이즈용 Microsoft 365 앱 업데이트 설치를 자동화합니다.

## <a name="mapping-contoso-business-needs-to-microsoft-365-for-enterprise"></a>엔터프라이즈를 위해 Contoso 비즈니스 요구 Microsoft 365 매핑

Contoso IT 부서는 배포 전에 비즈니스 요구 사항을 Microsoft 365 E5 매핑하기로 결정했습니다.


| 범주 | 비즈니스 요구 | Microsoft 365 제품 또는 기능에 대한 데이터 관리 |
|:-------|:-----|:-----|
| 생산성 |  |  |
|  | 보다 쉽게 공동으로 작업 | Microsoft Teams, SharePoint, OneDrive |
|  | 원격 및 모바일 작업자의 생산성 향상 | Microsoft 365 워크로드 및 클라우드 기반 데이터 |
|  | 창의성 및 혁신 증대 | Windows Ink, Cortana at Work, PowerPoint |
| 보안 |  |  |
|  | ID 및 액세스 관리 | Azure AD MFA(Multi-Factor Authentication) 및 Azure PIM(Azure AD 2013)Privileged Identity Management 전용 전역 관리자 계정 <BR> 모든 사용자 계정에 대한 MFA <BR> 조건부 액세스 <BR> 보안 읽기 권한자 <BR> Windows Hello <BR> Windows Credential Guard |
|  | 위협 방지 | Advanced Threat Analytics <BR> Windows Defender <BR> Office 365용 Defender <BR> Office 365용 Microsoft Defender <BR> Microsoft 365 조사 및 대응 <BR> |
|  | 정보 보호 | Azure Information Protection <BR> DLP(데이터 손실 방지) <BR> WIP(Windows Information Protection) <BR> Microsoft Cloud App Security <BR> Microsoft Intune |
|  | 보안 관리 | Azure Defender  <BR> Windows Defender 보안 센터 |
| 원격 및 모바일 액세스 및 비즈니스 파트너 |  |  |
|  | 원격 및 모바일 작업자를 위한 향상된 보안 | Microsoft Intune |
|  | 직원을 위한 원격 액세스 인프라 감소 | Microsoft 365 워크로드 및 클라우드 기반 데이터 |
|  | B2B 트랜잭션에 대한 연결 향상 및 오버헤드 감소 | 페더레이션된 인증 및 클라우드 기반 리소스 |
| 규정 준수 |  |  |
|  | 지역별 규정 준수 | GDPR의 Microsoft 365 |
| 관리 |  |  |
|  | 클라이언트 업데이트 설치를 위한 IT 오버헤드 감소 | Windows 10 Enterprise 업데이트 <BR> Microsoft Office 365 ProPlus 업데이트 |
||||

## <a name="next-step"></a>다음 단계

Contoso [Corporation의](contoso-networking.md) 사내 네트워크와 클라우드 기반 리소스에 대한 액세스 및 대기 시간에 최적화된 Microsoft 365 대해 자세히 알아보습니다.

## <a name="see-also"></a>참고 항목

[엔터프라이즈용 Microsoft 365 개요](microsoft-365-overview.md)

[테스트 랩 가이드](m365-enterprise-test-lab-guides.md)
