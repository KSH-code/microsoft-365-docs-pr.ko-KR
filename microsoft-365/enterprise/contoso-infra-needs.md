---
title: Contoso의 IT 인프라 및 비즈니스 요구 사항
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso 온-프레미스 IT 인프라의 기본 구조와 Microsoft 365 Enterprise로 해당 비즈니스 요구를 충족하는 방법을 이해합니다.
ms.openlocfilehash: bd259f367cdf3417e32671457f248029c853b6f8
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283683"
---
# <a name="contosos-it-infrastructure-and-business-needs"></a>Contoso의 IT 인프라 및 비즈니스 요구 사항

**요약:** Contoso 온-프레미스 IT 인프라의 기본 구조와 Microsoft 365 Enterprise로 해당 비즈니스 요구를 충족하는 방법을 이해합니다.


Contoso는 중앙 집중식 온-프레미스 IT 인프라에서 클라우드 기반 개인 생산성 워크로드 및 응용 프로그램을 통합하는 클라우드 포함 인프라로의 전환을 진행하고 있습니다.

## <a name="contosos-existing-it-infrastructure"></a>Contoso의 기존 IT 인프라

Contoso는 주로 중앙 집중식 온-프레미스 IT 인프라를 사용하며, 응용 프로그램 데이터 센터는 파리 본사에 있습니다.

그림 1에서는 데이터 센터, DMZ 및 인터넷이 구비된 본사 사무실을 볼 수 있습니다.

![](./media/contoso-infra-needs/contoso-infra-needs-fig1.png)

**그림 1: Contoso의 기존 IT 인프라**
 
온-프레미스 응용 프로그램 데이터 센터에서는 다음과 같은 것들을 호스팅합니다. 

- SQL Server 및 기타 Linux 데이터베이스를 사용하는 사용자 지정 LOB(기간 업무) 응용 프로그램
- 레거시 SharePoint 서버 집합
- 파일 저장을 위한 조직 및 팀 수준 서버

또한 비슷한 응용 프로그램 집합으로 서버 집합을 지원하는 각 지역의 허브 사무실. 이러한 서버는 지역의 IT 부서에서 관리합니다.

이러한 별도의 다중 지역 데이터 센터에 있는 응용 프로그램 및 데이터에 대한 검색 가능성은 계속해서 해결 과제로 남아 있습니다.

Contoso의 본사 DMZ에서는 각 서버 집합이 다음을 제공합니다.

- 파리 본사 직원을 위한 Contoso 인트라넷 및 웹 프록시에 대한 VPN 기반 원격 액세스 기능
- Contoso 공용 웹 사이트 호스팅 기능. 이러한 사이트에서 고객이 제품, 부품, 소모품 또는 서비스를 주문할 수 있습니다.
- 파트너와의 정보 교환 및 공동 작업을 위한 Contoso 파트너 엑스트라넷 호스팅 기능

## <a name="contosos-business-needs"></a>Contoso의 비즈니스 요구 사항

Contoso의 비즈니스 요구 사항은 다섯 가지 주요 범주로 나뉩니다.

생산성:

- 보다 쉽게 공동으로 작업

  전자 메일 및 파일 공유 기반 공동 작업을 실시간으로 문서 변경, 보다 간편해진 온라인 모임, 캡처한 대화 스레드를 지원하는 온라인 모델로 대체합니다.
- 원격 및 모바일 작업자의 생산성 향상

  많은 직원들이 가정 또는 현장에서 작업하는 경우, 병목 상태가 나타나는 VPN 솔루션을 클라우드의 Contoso 데이터 및 리소스 액세스 방식으로 대체하여 성능을 높입니다.
- 창의성 및 혁신 증대

  수동 입력과 3D 시각화를 포함하여 최신 수준의 시각적 학습 및 아이디어 개발 방식을 활용할 수 있습니다.


보안:

- ID 및 액세스 관리

  다중 요소 및 기타 형태의 인증을 적용하고 사용자 및 관리자 계정 자격 증명을 보호합니다.

- 위협 방지

  맬웨어를 포함하는 외부 보안 위협으로부터 보호 -> 맬웨어를 포함하여 외부 보안 위협으로부터 보호

- 정보 보호

  고객 데이터, 디자인 사양 및 직원 정보와 같은 고가치 디지털 자산에 대한 액세스를 잠그고 암호화합니다.

- 보안 관리

  보안 환경을 모니터링하고 위협을 실시간으로 감지하고 대응할 수 있습니다.

원격 및 모바일 액세스 및 비즈니스 파트너:

- 원격 및 모바일 작업자를 위한 향상된 보안

  BYOD(Bring Your Own Device) 및 회사 소유의 장치 관리를 도입하여 보안 액세스, 올바른 응용 프로그램 동작 및 회사 데이터 보호를 보장합니다.

- 직원을 위한 원격 액세스 인프라 감소

  일반적으로 액세스하는 리소스를 클라우드로 이동하여 유지 관리 및 지원 비용을 절감하고 원격 액세스 솔루션의 성능을 향상시킵니다.

- B2B(기업 간) 거래에 대해 더 나은 연결 제공 및 오버헤드 감소

  페더레이션 인증을 사용하는 클라우드 기반 솔루션으로 노후되고 비용이 많이 드는 파트너 엑스트라넷을 교체합니다.

규정 준수

- 지역별 규정 준수

  데이터 저장소, 암호화, 데이터 개인 정보 보호에 대한 업계 및 지역별 규정과 개인 데이터 규정[예: 유럽 연합을 위한 GDPR(일반 데이터 보호 규정)]을 준수합니다.

관리:

- 클라이언트 PC 및 장치에서 실행되는 소프트웨어를 관리하기 위한 IT 오버헤드를 줄입니다.

  조직 전체에서 Windows 운영 체제 및 Microsoft Office의 업데이트 설치를 자동화합니다.

## <a name="mapping-contosos-business-needs-to-microsoft-365-enterprise"></a>Contoso의 비즈니스 요구 사항에 맞는 Microsoft 365 Enterprise 제품 찾기

Contoso의 IT 부서는 배포 전에 비즈니스 요구에 맞는 다음과 같은 Microsoft 365 Enterprise E5 기능을 파악했습니다.

||||
|:-------|:-----|:-----|
| **범주** | **비즈니스 요구** | **Microsoft 365 Enterprise 제품 또는 기능** |
| 생산성 |  |  |
|  | 보다 쉽게 공동으로 작업 | Teams, SharePoint Online, 비즈니스용 Skype Online |
|  | 원격 및 모바일 작업자의 생산성 향상 | Office 365 워크로드 및 클라우드 기반 데이터 |
|  | 창의성 및 혁신 증대 | Windows Ink, Cortana at Work, PowerPoint |
| 보안 |  |  |
|  | ID 및 액세스 관리 | MFA(Multi-Factor Authentication) 및 Azure PIM(Privileged Identity Management다)를 포함하는 전용 전역 관리자 계정 <BR> 모든 사용자 계정에 대한 MFA <BR> 조건부 액세스 <BR> Windows Hello <BR> Windows Credential Guard |
|  | 위협 방지 | Advanced Threat Analytics <BR> Windows Defender <BR> Advanced Threat Protection <BR> Office 365 Advanced Threat Protection <BR> Office 365 위협 조사 및 응답 <BR> |
|  | 정보 보호 | Azure 정보 보호 <BR> Office 365 DLP(데이터 손실 방지) <BR> Windows Information Protection <BR> Microsoft Cloud App Security <BR> Office 365 CAS(Cloud App Security) <BR> Microsoft Intune |
|  | 보안 관리 | Azure Security Center  <BR> Windows Defender 보안 센터 |
| 원격 및 모바일 액세스 및 비즈니스 파트너 |  |  |
|  | 원격 및 모바일 작업자를 위한 향상된 보안 | Microsoft Intune |
|  | 직원을 위한 원격 액세스 인프라 감소 | Office 365 워크로드 및 클라우드 기반 데이터 |
|  | B2B 거래에 대해 더 나은 연결 제공 및 오버헤드 감소 | 페더레이션된 인증 및 클라우드 기반 리소스 |
| 규정 준수 |  |  |
|  | 지역별 규정 준수 | Office 365의 GDPR 기능 |
| 관리 |  |  |
|  | 클라이언트 업데이트 설치에 대한 IT 오버헤드 감소 | 배포 링 <BR> Windows 10 현재 위치 업그레이드 및 Autopilot <BR> Office 365 ProPlus |
||||

## <a name="next-step"></a>다음 단계

Contoso Corporation의 온-프레미스 네트워크 및 이러한 네트워크가 조직 전체에서 Microsoft 365 클라우드 기반 리소스에 대해 최적화된 액세스 및 대기 시간을 지원하는 방식을 [자세히 알아봅니다](contoso-networking.md).

## <a name="see-also"></a>참고 항목

[배포 가이드](deploy-microsoft-365-enterprise.md)

[테스트 랩 가이드](m365-enterprise-test-lab-guides.md)
