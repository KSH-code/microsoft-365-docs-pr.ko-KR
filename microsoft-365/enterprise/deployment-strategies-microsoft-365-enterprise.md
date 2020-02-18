---
title: 엔터프라이즈용 Microsoft 365 기본 인프라 배포 전략
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 09/24/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 엔터프라이즈용 Microsoft 365 기본 인프라의 단계를 배포하는 몇 가지 방법을 알아봅니다.
ms.openlocfilehash: 765bba743485c13c65cd6377abe01f80f2df4c23
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067820"
---
# <a name="microsoft-365-for-enterprise-foundation-infrastructure-deployment-strategies"></a>엔터프라이즈용 Microsoft 365 기본 인프라 배포 전략

엔터프라이즈용 Microsoft 365 [기본 인프라](deploy-foundation-infrastructure.md)의 단계를 배포하고 사용자에게 그 기능과 소프트웨어, 서비스를 선보이는 방법에는 몇 가지가 있습니다. 조직과 기존 인프라의 규모에 따라 복잡한 대규모 작업이 될 수 있는 이 프로젝트 관리를 시작할 때 다음과 같은 배포 전략을 고려해 보세요.

- 직렬 배포
- 사용자 롤아웃이 중첩되지 않는 병렬 배포
- 사용자 롤아웃이 중첩되는 병렬 배포
- 인프라 선행 구현 및 엔드투엔드 구성의 롤아웃

전체 프로젝트를 관리하고 엔터프라이즈용 Microsoft 365의 비즈니스 이점을 빠르게 실현하기 위한 다음과 같은 전략을 참고하시기 바랍니다.

>[!Note]
>이 문서는 배포 전략을 일관된 방식으로 기술하기 위해 몇 가지 가정을 바탕으로 간소화하여 설명하고 있습니다. 여기에서 설명하는 배포 전략은 일반화된 방식이며, 구체적인 기간을 시사하거나 모든 조직과 상황에 적용될 수 있음을 암시하지 않습니다.
>

## <a name="elements-of-it-project-management-for-typical-enterprise-organizations"></a>일반적인 기업 조직에서 볼 수 있는 IT 프로젝트 관리의 요소

IT 인프라에는 백엔드 서비스, 그리고 최종 사용자를 대상으로 신규 또는 향상된 기능 및 설치된 소프트웨어의 롤아웃이 모두 포함됩니다. IT 부서에서는 일반적으로 체계적인 방식으로 IT 인프라의 여러 요소를 배포합니다. IT 인프라 요소를 성공적으로 배포하기 위한 한 가지 방법은 다음으로 구성됩니다.

- 파일럿 롤아웃 

  초기 인프라 구성을 파일럿 사용자에게 롤아웃하고, 테스트를 진행하고, 인프라 구성을 수정하는 과정이 포함됩니다.

- 사용자 롤아웃

  지역, 부서, 그룹 등을 기준으로 구성 또는 소프트웨어를 조직의 나머지 사용자에게 체계적으로 롤아웃하는 과정입니다.

파일럿 롤아웃에 포함된 사용자는 사용자 롤아웃에 포함된 사용자와 같지 않습니다.

이 문서에서는 아래와 같은 그림을 사용하여 각각의 롤아웃을 표현합니다. 

![파일럿 및 사용자 롤아웃의 정의를 나타내는 그래픽](../media/deployment-strategies-microsoft-365-enterprise/definitions.png) 

사용자 롤아웃 그래픽의 음영은 그룹, 부서, 지역과 같은 체계적인 기준을 바탕으로 0%부터 100%까지 조직의 백분율을 나타냅니다.

## <a name="deployment-strategies"></a>배포 전략

지금부터 다음과 같은 배포 전략을 설명합니다.

- 직렬 배포
- 사용자 롤아웃이 중첩되지 않는 병렬 배포
- 사용자 롤아웃이 중첩되는 병렬 배포
- 인프라 선행 구현 및 엔드투엔드 구성의 롤아웃

### <a name="serial-deployment"></a>직렬 배포

직렬 배포에서는 특정 단계가 모든 사용자에게 100% 배포된 후에 다음 단계로 넘어갑니다. 직렬 배포를 사용하는 이유는 다음과 같습니다.

- 위험 완화
- 한정된 리소스
- IT 부서 자금 주기
- IT 기술 종속성
- 비즈니스 변경 관리 및 최종 사용자의 저항

다음은 엔터프라이즈용 Microsoft 365 기본 인프라를 단순화한 직렬 배포의 2~6단계를 보여주는 Gantt 차트입니다.

![기초 인프라 2-6 단계의 직렬 배포](../media/deployment-strategies-microsoft-365-enterprise/serial.png) 
 
설명과 예시의 간소화를 위해 각 단계와 단계 내의 배포 세그먼트는 모두 동일한 시간 안에 완료된다고 가정했습니다.

>[!Note]
>1단계: 엔터프라이즈용 Microsoft 365 기본 인프라의 네트워킹은 IT 부서만 개입하는 단계입니다. 사용자는 Microsoft 클라우드 리소스로의 최적화된 연결이라는 이점을 누리긴 하나, 연결을 본격적으로 사용하지는 않습니다.
>

다음은 간단한 파일럿 사용자 환경을 보여주는 예제입니다.

- 12월부터 MFA를 위해 내 스마트폰을 사용해야 합니다. (ID)
- 3월에는 내 Windows 8.1 데스크톱에 Windows 10 Enterprise를 설치하게 됩니다. (Windows 10 Enterprise)
- 6월에는 Office 2013을 대체하는 Office 365 ProPlus가 설치됩니다. (Office 365 ProPlus)
- 9월에는 장치 등록과 앱 및 장치 정책이 적용됩니다. (모바일 장치 관리)
- 12월에는 Azure Information Protection 클라이언트가 설치되고, 문서에 레이블을 적용하는 방법을 교육받습니다. (정보 보호)

각 파일럿 롤아웃 단계는 90일 간격으로 진행됩니다.

다음은 간단한 최종 사용자 환경을 보여주는 예제입니다.

- 1월부터 MFA를 위해 내 스마트폰을 사용해야 합니다. (ID)
- 4월에는 내 Windows 8.1 데스크톱에 Windows 10 Enterprise를 설치하게 됩니다. (Windows 10 Enterprise)
- 7월에는 Office 2013을 대체하는 Office 365 ProPlus가 설치됩니다. (Office 365 ProPlus)
- 10월에는 장치 등록과 앱 및 장치 정책이 적용됩니다. (모바일 장치 관리)
- 다음 해 1월에는 Azure Information Protection 클라이언트가 설치되고, 문서에 레이블을 적용하는 방법을 교육받습니다. (정보 보호)

각 최종 사용자 롤아웃 단계는 90일 간격으로 진행됩니다.

엔터프라이즈용 Microsoft 365 기본 인프라가 완전히 배포되기까지 시간이 오래 걸릴 수 있다는 것이 이 직렬 배포 전략의 단점입니다.

### <a name="parallel-deployment-with-non-overlapping-user-rollout-parallel-1"></a>사용자 롤아웃이 중첩되지 않는 병렬 배포 (병렬 1)

이 배포 전략에서는 현 단계의 사용자 롤아웃 중 마지막 부분이 진행되는 시점에 다음 단계의 파일럿 롤아웃을 시작합니다. 다음은 배포의 2~6단계에서 직전 단계의 사용자 롤아웃이 마무리되고 있는 시점에 파일럿 롤아웃이 시작되는 것을 보여주는 차트입니다.

![사용자 롤아웃이 중첩되지 않는 2-6 단계의 병렬 배포](../media/deployment-strategies-microsoft-365-enterprise/parallel1.png) 
 
이 배포 전략에서는 조직 전체에서 사용자 롤아웃의 현 단계가 완료된 후에 차기 단계가 시작됩니다. 파일럿 롤아웃에 포함되지 않은 사용자는 동시에 여러 개의 단계를 진행하지 않는 반면, 파일럿 롤아웃은 사용자 롤아웃과 병렬로 진행됩니다.

다음은 간단한 파일럿 사용자 환경을 보여주는 예제입니다.

- 12월부터 MFA를 위해 내 스마트폰을 사용해야 합니다. (ID)
- 2월에는 내 Windows 8.1 데스크톱에 Windows 10 Enterprise를 설치하게 됩니다. (Windows 10 Enterprise)
- 4월에는 Office 2013을 대체하는 Office 365 ProPlus가 설치됩니다. (Office 365 ProPlus)
- 6월에는 장치 등록과 앱 및 장치 정책이 적용됩니다. (모바일 장치 관리)
- 8월에는 Azure Information Protection 클라이언트가 설치되고, 문서에 레이블을 적용하는 방법을 교육받습니다. (정보 보호)

각 파일럿 롤아웃 단계는 60일 간격으로 진행됩니다.

다음은 간단한 최종 사용자 환경을 보여주는 예제입니다.

- 1월부터 MFA를 위해 내 스마트폰을 사용해야 합니다. (ID)
- 3월에는 내 Windows 8.1 데스크톱에 Windows 10 Enterprise를 설치하게 됩니다. (Windows 10 Enterprise)
- 5월에는 Office 2013을 대체하는 Office 365 ProPlus가 설치됩니다. (Office 365 ProPlus)
- 7월에는 장치 등록과 앱 및 장치 정책이 적용됩니다. (모바일 장치 관리)
- 9월에는 Azure Information Protection 클라이언트가 설치되고, 문서에 레이블을 적용하는 방법을 교육받습니다. (정보 보호)

각 최종 사용자 롤아웃 단계는 60일 간격으로 진행됩니다.

IT 부서와 사용자들이 동시에 여러 건의 롤아웃을 진행할 필요가 없으면서도 엔터프라이즈용 Microsoft 365 기본 인프라가 완전히 배포되기까지 시간이 비교적 짧게 걸린다는 것이 이 배포 전략의 장점입니다.

### <a name="parallel-deployment-with-overlapping-user-rollout-parallel-2"></a>사용자 롤아웃이 중첩되는 병렬 배포(병렬 2)

이 배포 전략에서는 차기 단계의 파일럿 롤아웃과 사용자 롤아웃이 다음과 같이 시작됩니다.

- 현 단계의 사용자 롤아웃 중 마지막 부분이 진행되는 시점에 차기 단계의 파일럿 롤아웃이 시작됩니다.
- 사용자들이 여러 단계의 롤아웃에 동시에 참여하지 않는 방식으로 현 단계의 사용자 롤아웃이 진행되는 시점에 차기 단계의 사용자 롤아웃이 시작됩니다. 여기에서는 지역, 부서 또는 기타 그룹화를 사용하여 동일한 방식으로 기본 인프라의 각 단계를 배포한다고 가정합니다.

다음은 세 가지 배포 전략을 간단하게 비교한 차트입니다.

![사용자 롤아웃이 중첩되는 2-6 단계의 병렬 배포](../media/deployment-strategies-microsoft-365-enterprise/parallel2.png) 

이 배포 전략의 최종 결과는 다음과 같습니다.

- 파일럿 롤아웃은 중단 없이 현 단계에서 차기 단계로 넘어갑니다.
- 직전 단계의 사용자 롤아웃이 완료되기 전에 차기 단계의 사용자 롤아웃이 시작되나, 각 사용자는 한 번에 하나의 단계에만 참여합니다.

다음은 간단한 파일럿 사용자 환경을 보여주는 예제입니다.

- 12월부터 MFA를 위해 내 스마트폰을 사용해야 합니다. (ID)
- 1월에는 내 Windows 8.1 데스크톱에 Windows 10 Enterprise를 설치하게 됩니다. (Windows 10 Enterprise)
- 2월에는 Office 2013을 대체하는 Office 365 ProPlus가 설치됩니다. (Office 365 ProPlus)
- 3월에는 장치 등록과 앱 및 장치 정책이 적용됩니다. (모바일 장치 관리)
- 4월에는 Azure Information Protection 클라이언트가 설치되고, 문서에 레이블을 적용하는 방법을 교육받습니다. (정보 보호)

각 파일럿 롤아웃 단계는 30일 간격으로 진행됩니다.

다음은 간단한 최종 사용자 환경을 보여주는 예제입니다.

- 1월부터 MFA를 위해 내 스마트폰을 사용해야 합니다. (ID)
- 2월에는 내 Windows 8.1 데스크톱에 Windows 10 Enterprise를 설치하게 됩니다. (Windows 10 Enterprise)
- 3월에는 Office 2013을 대체하는 Office 365 ProPlus가 설치됩니다. (Office 365 ProPlus)
- 4에는 장치 등록과 앱 및 장치 정책이 적용됩니다. (모바일 장치 관리)
- 5월에는 Azure Information Protection 클라이언트가 설치되고, 문서에 레이블을 적용하는 방법을 교육받습니다. (정보 보호)

각 최종 사용자 롤아웃 단계는 30일 간격으로 진행됩니다.

최종 사용자가 동시에 여러 건의 롤아웃을 진행할 필요가 없으면서도 엔터프라이즈용 Microsoft 365 기본 인프라가 완전히 배포되기까지 시간이 비교적 짧게 걸린다는 것이 이 배포 전략의 장점입니다. 그러나 연속적인 단계 사이의 휴식은 없습니다.

### <a name="up-front-infrastructure-and-rollout-of-the-end-to-end-configuration"></a>인프라 선행 구현 및 엔드투엔드 구성의 롤아웃

하나의 배포 세그먼트에 2~6단계를 압축하여 진행할 수 있는 소규모 조직에서는 다음과 같은 배포 전략을 구현할 수 있습니다.
 
![인프라 선행 구현 및 엔드투엔드 구성의 롤아웃](../media/deployment-strategies-microsoft-365-enterprise/up-front.png) 

IT 부서가 2~6단계의 인프라를 구성한 다음 엔드투엔드 기능의 점검을 위해 파일럿 사용자에게 구성을 롤아웃합니다. 따라서 사용자는 다음과 같은 기능을 한꺼번에 이용하게 됩니다.

- MFA 및 기타 ID 기능 (ID)
- Windows 장치의 Windows 10 Enterprise (Windows 10 Enterprise)
- Office 제품군으로서 Office 365 ProPlus (Office 365 ProPlus)
- 앱 및 장치 정책(모바일 장치 관리)
- Azure Information Protection 클라이언트 설치 및 문서에 레이블을 적용하는 방법에 관한 교육 (정보 보호)

파일럿 롤아웃이 완료되면 사용자 롤아웃이 시작되어 각 사용자가 동시에 모든 기능을 이용하게 됩니다.

## <a name="next-step"></a>다음 단계

[기본 인프라](deploy-foundation-infrastructure.md)를 사용하여 엔터프라이즈용 Microsoft 365의 배포를 시작하세요.
