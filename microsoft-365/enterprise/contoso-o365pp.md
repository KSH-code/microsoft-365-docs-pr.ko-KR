---
title: Contoso용 엔터프라이즈용 Microsoft 365 앱 배포
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso에서 Microsoft Endpoint Configuration Manager를 사용하여 엔터프라이즈용 Microsoft 365 앱을 배포하는 방식을 이해합니다.
ms.openlocfilehash: de6a5348a49a490afa3c3ac632e66026966e2ef3
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695161"
---
# <a name="microsoft-365-apps-for-enterprise-deployment-for-contoso"></a>Contoso용 엔터프라이즈용 Microsoft 365 앱 배포

Contoso는 보다 효과적인 공동 작업, 더 나은 보안 및 최신 데스크톱 환경을 사용하기 위해 PC를 Windows 10 Enterprise 및 엔터프라이즈용 Microsoft 365 앱으로 업그레이드했습니다. Contoso는 해당 인프라 및 비즈니스 요구를 파악한 후 배포에 대한 다음과 같은 주요 요구 사항을 파악했습니다.

- 모든 PC에서 엔터프라이지용 Microsoft 365 앱을 실행해야 합니다.
- 가능한 경우 기존 관리 도구와 인프라를 사용해서 배포합니다.
- 배포는 최종 사용자 장치에서 여러 언어 및 기존 아키텍처를 지원해야 합니다.
- PC는 최소한의 IT 관리 비용을 들이고 최종 사용자에게 최소한의 영향을 미치면서 최신 상태로 안전하게 유지해야 합니다.

## <a name="deployment-tools"></a>배포 도구

Contoso는 해당 요구 사항을 토대로, Configuration Manager(현재 분기)를 사용하여 Windows 10 Enterprise 및 엔터프라이즈용 Microsoft 365 앱을 배포하기로 선택했습니다. Configuration Manager는 대규모 환경에 맞게 확장되며, 설치, 업데이트 및 설정을 포괄적으로 제어할 수 있도록 합니다. 그뿐 아니라 Office를 보다 쉽고 효율적으로 배포 및 관리할 수 있도록 하는 다음과 같은 기본 기능도 제공합니다.

- 피어 캐시: 원격 위치에 장치를 배포할 때 네트워크 용량이 제한적인 경우 도움이 될 수 있습니다.
- Office 클라이언트 관리 대시보드: Office를 쉽게 배포하고 업데이트를 모니터링할 수 있도록 하고, 관리자에게 최신 배포 및 관리 기능에 대한 액세스 권한을 부여합니다.
- 지능형 언어 팩 배포: 운영 체제와 동일한 언어를 자동으로 배포하는 기능을 포함합니다.
- 배포 중에 클라이언트에서 기존 버전의 Office를 제거하기 위한 완전히 지원되는 편리한 방법

Contoso는 Configuration Manager 외에도, Microsoft에서 무료로 제공하는 [Readiness Toolkit](https://docs.microsoft.com/deployoffice/readiness-toolkit-application-compatibility-microsoft-365-apps)를 사용하여 Office 매크로 및 추가 기능에 대한 호환성 문제를 평가했습니다.

## <a name="managing-the-deployment-and-updates"></a>배포 및 업데이트 관리

엔터프라이즈용 Microsoft 365 앱에는 새 릴리스 모델인 Office가 서비스로 포함되어 있습니다. 이 서비스 모델을 사용하면 새 기능을 손쉽게 최신 상태로 유지할 수 있지만 새 릴리스를 배포 및 테스트하는 방식에 대한 IT 부서의 접근 방식을 변경해야 하는 경우가 종종 발생합니다. 호환성 문제를 최소화하고 컴퓨터를 최신 상태로 유지하기 위해 Contoso는 다음의 두 단계에 걸쳐 Windows 및 Office를 배포했습니다. 

- 첫 번째 단계에서는 조직의 소규모 대표 장치 집합에 엔터프라이즈용 Microsoft 365 앱을 배포했습니다. 이 파일럿 그룹은 엔터프라이즈용 Microsoft 365 앱에서 앱, 추가 기능 및 하드웨어를 테스트하는 데 사용되었습니다.
- 4개월 후에 파일럿 그룹에서 앱, 추가 기능 및 하드웨어의 모든 중요한 문제를 해결한 다음, Contoso는 조직의 나머지 장치에 엔터프라이즈용 Microsoft 365 앱을 배포했습니다(광범위한 그룹). 

Configuration Manager를 사용하여 Office에 대한 업데이트를 관리하는 대신, Contoso는 클라우드에서 자동 업데이트를 사용하도록 설정했습니다. 클라우드 기반 업데이트는 장치를 최신 상태로 유지하면서 관리 오버헤드를 줄였습니다. 

Contoso는 기능 업데이트를 위해서도 Office 배포에 사용한 것과 동일한 2단계 접근 방법을 따랐습니다. 즉, 파일럿 그룹의 장치가 조직의 나머지 장치(브로드 그룹)보다 4개월 먼저 기능 업데이트를 받았습니다. Office에 대해 이러한 방식을 적용하기 위해 Contoso는 권장되는 두 개의 [업데이트 채널](https://docs.microsoft.com/DeployOffice/overview-update-channels)을 사용했습니다. 

- 파일럿 그룹에 대한 업데이트용 반기 엔터프라이즈 채널(미리 보기) 
- 광범위한 그룹에 대한 업데이트용 반기 엔터프라이즈 채널. 

반기 엔터프라이즈 채널(미리 보기)은 반기 엔터프라이즈 채널보다 4개월 먼저 엔터프라이즈용 Microsoft 365 앱 버전을 릴리스하므로, Contoso는 업데이트를 관리할 필요가 없이 유효성을 검사할 시간적 여유를 갖게 됩니다. 

## <a name="deployment-process"></a>배포 프로세스

Office 배포를 완료하기 위해 Contoso는 Microsoft의 모범 사례 권장 사항을 포함하는 다음 프로세스를 구현했습니다.

1. 배포 전에, 준비 도구 키트를 사용하여 앱 및 Office 추가 기능이 엔터프라이즈용 Microsoft 365 앱과 호환되는지 평가했습니다.
2. Configuration Manager에서 Contoso는 클라이언트 장치에 피어 캐시를 사용하도록 설정하여 원격 위치의 클라이언트 장치에 배포할 때 제한적인 네트워크 용량 때문에 발생하는 문제를 완화했습니다. 
3. 또한 Configuration Manager에서 두 가지 배포 그룹, 즉 파일럿 그룹과 광범위한 그룹을 장치 컬렉션으로 정의했습니다. 조직 내의 소규모 대표 장치 집합을 포함하는 파일럿 그룹은 Windows 10 Enterprise 및 엔터프라이즈용 Microsoft 365 앱에서 앱, 추가 기능 및 하드웨어를 추가적으로 테스트하는 데 사용되었습니다. 
4. 그들은 Configuration Manager 콘솔에 포함되어 있는 Office 클라이언트 관리 대시보드 및 Office 365 설치 관리자 마법사를 사용하여 Office용 배포 패키지를 만들었습니다. 또한 두 개의 엔터프라이즈용 Microsoft 365 앱 패키지, 즉 반기 엔터프라이즈 채널(미리 보기)의 파일럿 그룹용 패키지와 반기 엔터프라이즈 채널의 광범위한 그룹용 패키지를 만들었습니다. 
5. 각 Office 패키지의 일부로, 영어, 프랑스어,및 독일어 언어 팩을 포함했습니다. 장치에 Office 패키지에 포함되지 않은 언어가 필요한 경우 Office CDN(콘텐츠 배달 네트워크)에서 자동으로 다운로드되었습니다.
6. 엔터프라이즈용 Microsoft 365 앱을 설치하기 전에 모든 기존 Office의 MSI 버전을 자동으로 제거하는 Office 패키지의 기본 제공 기능을 사용했습니다.
7. Configuration Manager에서 Windows 및 Office 패키지를 네트워크의 배포 지점에 배포한 후 Configuration Manager 배포 작업 시퀀스를 실행하여 파일럿 그룹에 파일럿 엔터프라이즈용 Microsoft 365 앱 패키지를 배포했습니다.
8. Contoso는 파일럿 그룹과의 호환성 문제를 해결한 후에 광범위한 엔터프라이즈용 Microsoft 365 앱 패키지를 광범위한 그룹에 배포하는 작업 시퀀스를 실행했습니다.

Contoso는 자동으로 클라우드로부터 장치를 업데이트하도록 선택했기 때문에 구성 관리자에서 프로세스를 관리할 필요가 없습니다. 그 장치는 초기 배포의 부분으로 정의된 업데이트 채널을 기반으로 한 클라우드로부터 직접적으로 자동 업데이트됩니다. 

Contoso의 엔터프라이즈용 Microsoft 365 앱 설치 및 지속적인 업데이트 배포 아키텍처는 다음과 같습니다.

![Contoso의 엔터프라이즈용 Microsoft 365 앱 배포 인프라](../media/contoso-o365pp/contoso-o365pp-fig1.png)
 
## <a name="next-step"></a>다음 단계

Contoso가 Microsoft 365의 microsoft Intune을 사용 하 여 해당 장치 및 조직에서 실행 되는 앱을 관리 하는 방법을 [알아봅니다](contoso-mdm.md) .

## <a name="see-also"></a>참고 항목

[Microsoft Office 365 ProPlus](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps)

[엔터프라이즈용 Microsoft 365 개요](microsoft-365-overview.md)

[테스트 랩 가이드](m365-enterprise-test-lab-guides.md)
