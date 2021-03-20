---
title: Contoso용 엔터프라이즈용 Microsoft 365 앱 배포
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso에서 Microsoft Endpoint Configuration Manager를 사용하여 엔터프라이즈용 Microsoft 365 앱을 배포하는 방식을 이해합니다.
ms.openlocfilehash: 71958b2e87882e478a852db1f906f61207837854
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907677"
---
# <a name="microsoft-365-apps-for-enterprise-deployment-for-contoso"></a>Contoso용 엔터프라이즈용 Microsoft 365 앱 배포

Contoso는 더 효과적인 공동 작업, 더 나은 보안 및 최신 데스크톱 환경을 지원하기 위해 PC를 Windows 10 Enterprise 및 엔터프라이즈용 Microsoft 365 앱으로 업그레이드했습니다. Contoso는 인프라 및 비즈니스 요구 사항을 평가한 후 배포에 대한 다음 주요 요구 사항을 확인했습니다.

- 모든 PC는 엔터프라이즈용 Microsoft 365 앱을 실행해야 합니다.
- 배포는 가능한 경우 기존 관리 도구 및 인프라를 사용해야 합니다.
- 배포는 사용자 장치에서 여러 언어 및 기존 아키텍처를 지원해야 합니다.
- PC는 IT 관리 비용을 최소화하고 사용자에게 미치는 영향을 최소화하면서 최신 보안 유지해야 합니다.

## <a name="deployment-tools"></a>배포 도구

Contoso는 요구 사항에 따라 Configuration Manager(현재 분기)를 통해 Windows 10 Enterprise 및 엔터프라이즈용 Microsoft 365 앱을 배포하기로 선택했습니다. 구성 관리자는 대규모 환경에 맞춰 확장되고 설치, 업데이트 및 설정에 대한 광범위한 컨트롤을 제공합니다. 또한 다음과 같은 Office를 보다 쉽고 효율적으로 배포하고 관리할 수 있도록 하는 기본 제공 기능도 제공합니다.

- 피어 캐시 - 원격 위치의 장치에 배포할 때 제한된 네트워크 용량에 도움이 될 수 있습니다.
- Office 클라이언트 관리 대시보드에서는 Office를 쉽게 배포하고 업데이트를 모니터링하고 관리자에게 최신 배포 및 관리 기능에 액세스할 수 있습니다.
- 지능형 언어 팩 배포(운영 체제와 동일한 언어 자동 배포 포함)
- 배포 중에 클라이언트에서 기존 버전의 Office를 제거하는 완전히 지원되는 사용이 간편한 방법입니다.

Contoso는 Configuration Manager 외에도 Microsoft의 무료 도구인 Office Toolkit [및 VBA에](/deployoffice/readiness-toolkit-application-compatibility-microsoft-365-apps)대한 Readiness Toolkit 를 사용하여 Office 매크로 및 추가 기능의 호환성 문제를 평가했습니다.

## <a name="managing-deployment-and-updates"></a>배포 및 업데이트 관리

엔터프라이즈용 Microsoft 365 앱에는 새로운 릴리스 모델인 Office as a Service가 있습니다. 이 서비스 모델을 사용하면 새로운 기능을 간편하게 최신으로 유지 할 수 있습니다. 그러나 IT 부서에서 새 릴리스를 배포하고 테스트하는 방법을 변경해야 하는 경우가 종종 있습니다. 호환성 문제를 최소화하고 컴퓨터를 최신으로 유지하기 위해 Contoso는 다음 두 단계로 Windows 및 Office를 배포했습니다.

- 먼저, 조직 전체의 소규모 대표 장치 집합에 엔터프라이즈용 Microsoft 365 앱을 배포했습니다. 이 파일럿 그룹은 엔터프라이즈용 Microsoft 365 앱을 사용하여 앱, 추가 기능 및 하드웨어를 테스트하는 데 사용했습니다.
- 4개월 후에 파일럿 그룹에서 앱, 추가 기능 및 하드웨어의 모든 중요한 문제를 해결한 다음, Contoso는 조직의 나머지 장치에 엔터프라이즈용 Microsoft 365 앱을 배포했습니다(광범위한 그룹).

Contoso는 Configuration Manager를 사용하여 Office에 대한 업데이트를 관리하는 대신 클라우드에서 자동 업데이트를 사용하도록 설정했습니다. 클라우드 기반 업데이트는 장치를 최신으로 유지하면서 관리 오버헤드를 줄입니다.

Contoso는 Office 배포에 사용한 기능 업데이트와 동일한 2단계 접근 방식을 따랐습니다. 파일럿 그룹의 장치는 나머지 조직의 장치(브로드 그룹)보다 4개월 일찍 기능 업데이트를 수신했습니다. Office에서 이 기능을 사용하도록 설정하기 위해 Contoso는 두 개의 권장 업데이트 [채널을 사용했습니다.](/DeployOffice/overview-update-channels)

- 파일럿 그룹에 대한 업데이트용 반기 엔터프라이즈 채널(미리 보기)
- Semi-Annual 업데이트용 엔터프라이즈 채널

반기 엔터프라이즈 채널(미리 보기)은 반기 엔터프라이즈 채널보다 4개월 먼저 엔터프라이즈용 Microsoft 365 앱 버전을 릴리스하므로, Contoso는 업데이트를 관리할 필요가 없이 유효성을 검사할 시간적 여유를 갖게 됩니다.

## <a name="deployment-process"></a>배포 프로세스

Office 배포를 완료하기 위해 Contoso는 Microsoft의 모범 사례 권장 사항을 포함하는 다음 프로세스를 구현했습니다.

1. 배포 전에 Contoso는 Office 추가 Toolkit 및 VBA용 Readiness 앱을 사용하여 앱 및 Office 추가 기능을 테스트하여 엔터프라이즈용 Microsoft 365 앱과의 호환성을 평가했습니다.
1. Configuration Manager에서는 클라이언트 디바이스에서 피어 캐시를 사용하도록 설정하여 원격 위치의 클라이언트 장치에 배포할 때 제한된 네트워크 용량에 도움이 됩니다. 
1. Contoso는 Configuration Manager에서 두 개의 배포 그룹을 장치 모음으로 정의했습니다. 파일럿 그룹과 광범위한 그룹입니다. 조직 전체에 소수의 대표 장치 집합이 포함된 파일럿 그룹은 Windows 10 Enterprise 및 엔터프라이즈용 Microsoft 365 앱을 사용하여 앱, 추가 기능 및 하드웨어를 추가로 테스트하는 데 사용되었습니다.
1. 또한 Configuration Manager 콘솔의 일부인 Office 클라이언트 관리 대시보드 및 Office 365 설치 관리자 마법사를 사용하여 Office용 배포 패키지를 만들 수 있습니다. 두 개의 엔터프라이즈용 Microsoft 365 앱 패키지를 구축했습니다. 하나는 Semi-Annual Enterprise 채널(미리 보기)의 파일럿 그룹용 패키지와 Semi-Annual Enterprise 채널의 광범위한 그룹용입니다.
2. 각 Office 패키지에는 영어, 프랑스어 및 독일어 언어 팩이 포함되어 있습니다. 장치에 Office 패키지에 포함되지 않은 언어가 필요한 경우 해당 언어 팩은 Office CDN(콘텐츠 배달 네트워크)에서 자동으로 다운로드됩니다.
3. 엔터프라이즈용 Microsoft 365 앱을 설치하기 전에 모든 기존 Office의 MSI 버전을 자동으로 제거하는 Office 패키지의 기본 제공 기능을 사용했습니다.
4. Configuration Manager에서 네트워크의 배포 지점에 Windows 및 Office 패키지를 배포했습니다. 그런 다음 Configuration Manager 배포 작업 순서를 실행하여 파일럿 엔터프라이즈용 Microsoft 365 앱 패키지를 파일럿 그룹에 배포했습니다.
5. 파일럿 그룹과의 호환성 문제를 해결한 후 Contoso는 엔터프라이즈용 Microsoft 365 앱 패키지를 광범위 그룹에 배포하는 작업 순서를 실행했습니다.

Contoso는 자동으로 클라우드로부터 장치를 업데이트하도록 선택했기 때문에 구성 관리자에서 프로세스를 관리할 필요가 없습니다. 해당 장치는 초기 배포에 정의된 업데이트 채널을 기반으로 클라우드에서 직접 자동으로 업데이트됩니다.

다음은 엔터프라이즈용 Contoso Microsoft 365 앱 설치 및 지속적인 업데이트 배포 아키텍처입니다.

![엔터프라이즈용 Microsoft 365 앱에 대한 Contoso 배포 인프라](../media/contoso-o365pp/contoso-o365pp-fig1.png)
 
## <a name="next-step"></a>다음 단계

Contoso가 엔터프라이즈용 Microsoft 365의 [Microsoft Intune을](contoso-mdm.md) 사용하여 조직 전체에서 실행되는 장치 및 앱을 관리하는 방법을 알아보습니다.

## <a name="see-also"></a>참고 항목

[Microsoft Office 365 ProPlus](/deployoffice/deployment-guide-microsoft-365-apps)

[엔터프라이즈용 Microsoft 365 개요](microsoft-365-overview.md)

[테스트 랩 가이드](m365-enterprise-test-lab-guides.md)