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
ms.openlocfilehash: 2c02c28ddba7c24592ce09d87bf6f5c9df700a2a
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754357"
---
# <a name="microsoft-365-apps-for-enterprise-deployment-for-contoso"></a>Contoso용 엔터프라이즈용 Microsoft 365 앱 배포

Contoso는 Pc를 Windows 10 Enterprise로 업그레이드 하 고 Microsoft 365 앱을 사용 하 여 더욱 효율적인 공동 작업, 보안 강화, 보다 현대적인 데스크톱 환경을 사용할 수 있도록 했습니다. Contoso는 인프라 및 비즈니스 요구를 평가한 후 다음과 같은 주요 배포 요구 사항을 확인 했습니다.

- 모든 Pc에서 Microsoft 365 앱 for enterprise를 실행 해야 합니다.
- 가능한 경우 기존 관리 도구와 인프라를 사용 해야 합니다.
- 배포에서는 사용자 장치에서 여러 언어 및 기존 아키텍처를 지원 해야 합니다.
- Pc는 최소한의 IT 관리 비용 및 사용자에 게 최소한의 영향을 받아 최신 상태로 유지 되어야 합니다.

## <a name="deployment-tools"></a>배포 도구

요구 사항에 따라 Contoso는 Configuration Manager (현재 분기)를 통해 Windows 10 Enterprise 및 Microsoft 365 앱 for Enterprise를 배포 하기로 선택 했습니다. 구성 관리자는 대규모 환경에 맞게 확장 되며 설치, 업데이트 및 설정에 대 한 광범위 한 제어를 제공 합니다. 또한 다음을 비롯 하 여 보다 쉽고 효율적으로 Office를 배포 하 고 관리할 수 있도록 하는 기능이 기본적으로 제공 됩니다.

- 피어 캐시-원격 위치에 장치를 배포할 때 네트워크 용량을 제한 하는 데 도움이 될 수 있습니다.
- Office 클라이언트 관리 대시보드를 사용 하 여 간편 하 게 사무실을 배포 하 고 업데이트를 모니터링 하 고 관리자에 게 최신 배포 및 관리 기능에 대 한 액세스를 제공 합니다.
- 지능형 언어 팩 배포 (운영 체제와 동일한 언어를 자동으로 배포 하는 작업)
- 배포 중에 클라이언트에서 기존 버전의 Office를 제거 하기 위해 완벽 하 게 지원 되 고 사용이 편리한 방법입니다.

Contoso는 Configuration Manager 외에도 Microsoft에서 제공 하는 무료 도구로 office 매크로 및 추가 기능에 [대 한](https://docs.microsoft.com/deployoffice/readiness-toolkit-application-compatibility-microsoft-365-apps)호환성 문제를 평가 합니다

## <a name="managing-deployment-and-updates"></a>배포 및 업데이트 관리

Microsoft 365 enterprise 용 앱에는 새로운 릴리스 모델인 Office (서비스)가 있습니다. 서비스 모델을 사용 하면 새로운 기능을 통해 최신 상태로 유지 하는 데 도움이 됩니다. 하지만 IT 부서가 새 릴리스를 배포 하 고 테스트 하는 방법을 변경 해야 하는 경우가 많습니다. 호환성 문제를 최소화 하 고 컴퓨터를 최신 상태로 유지 하려면 Contoso는 2 단계를 통해 Windows와 Office를 배포 해야 합니다.

- 먼저 조직 전체에서 소규모 대표 장치 집합에 Microsoft 365 앱을 배포 했습니다. 이 파일럿 그룹은 Microsoft 365 앱 for enterprise 용 앱, 추가 기능 및 하드웨어를 테스트 하는 데 사용 되었습니다.
- 4개월 후에 파일럿 그룹에서 앱, 추가 기능 및 하드웨어의 모든 중요한 문제를 해결한 다음, Contoso는 조직의 나머지 장치에 엔터프라이즈용 Microsoft 365 앱을 배포했습니다(광범위한 그룹).

Contoso는 Configuration Manager를 사용 하 여 Office에 대 한 업데이트를 관리 하는 대신 클라우드에서 자동 업데이트를 사용 하도록 설정 합니다. 클라우드 기반 업데이트는 장치가 최신 상태로 유지 되도록 하면서 관리 오버 헤드를 줄여줍니다.

Contoso는 Office를 배포 하는 데 사용 되는 것과 동일한 2 단계 방식으로 기능 업데이트: 파일럿 그룹 수신 기능에 있는 장치는 나머지 조직 (광범위 그룹)의 장치 보다 4 개월 이전에 업데이트 됩니다. 이를 위해 Office에서이를 사용 하기 위해 Contoso는 두 가지 권장 [업데이트 채널](https://docs.microsoft.com/DeployOffice/overview-update-channels)을 사용 했습니다.

- 파일럿 그룹에 대한 업데이트용 반기 엔터프라이즈 채널(미리 보기)
- 광범위 한 그룹의 업데이트용 엔터프라이즈 채널 Semi-Annual

반기 엔터프라이즈 채널(미리 보기)은 반기 엔터프라이즈 채널보다 4개월 먼저 엔터프라이즈용 Microsoft 365 앱 버전을 릴리스하므로, Contoso는 업데이트를 관리할 필요가 없이 유효성을 검사할 시간적 여유를 갖게 됩니다.

## <a name="deployment-process"></a>배포 프로세스

Office 배포를 완료하기 위해 Contoso는 Microsoft의 모범 사례 권장 사항을 포함하는 다음 프로세스를 구현했습니다.

1. 배포 전에 Contoso는 Office 추가 기능의 준비 도구 키트 및 VBA를 사용 하 여 앱 및 Office 추가 기능을 테스트 하 고 Microsoft 365 앱 for enterprise와의 호환성을 평가 합니다.
1. Configuration Manager에서 클라이언트 장치에 피어 캐시를 사용 하도록 설정 하 여 원격 위치의 클라이언트 장치에 배포할 때 네트워크 용량을 제한 하는 데 도움을 줍니다. 
1. Contoso는 두 개의 배포 그룹을 구성 관리자의 장치 모음으로, 파일럿 그룹과 광범위 한 그룹으로 정의 했습니다. 조직 전체에 소수의 대표 장치 집합이 포함 된 파일럿 그룹은 Windows 10 Enterprise 및 Microsoft 365 앱 for enterprise 용 앱, 추가 기능 및 하드웨어에 대 한 추가 테스트를 위해 사용 되었습니다.
1. Office 클라이언트 관리 대시보드 및 office 365 설치 관리자 마법사 (Configuration Manager 콘솔의 모든 부분)를 사용 하 여 Office 용 배포 패키지를 만들었습니다. 엔터프라이즈 패키지에 대 한 Microsoft 365 앱을 두 개 구축 했으며, Semi-Annual 엔터프라이즈 채널 (미리 보기)의 파일럿 그룹 및 Semi-Annual 엔터프라이즈 채널의 광범위 한 그룹에 대해 하나씩 구성 되어 있습니다.
2. 각 Office 패키지에는 영어, 프랑스어 및 독일어 언어 팩이 포함 되어 있습니다. 장치에 Office 패키지에 포함 되지 않은 언어가 필요한 경우 Office CDN (콘텐츠 배달 네트워크)에서 해당 언어 팩을 자동으로 다운로드 합니다.
3. 엔터프라이즈용 Microsoft 365 앱을 설치하기 전에 모든 기존 Office의 MSI 버전을 자동으로 제거하는 Office 패키지의 기본 제공 기능을 사용했습니다.
4. Configuration Manager에서는 네트워크를 통해 Windows 및 Office 패키지를 배포 지점에 배포 했습니다. 그런 다음 Configuration Manager 배포 작업 순서를 실행 하 여 파일럿 그룹에 엔터프라이즈 패키지에 대 한 파일럿 Microsoft 365 앱을 배포 합니다.
5. Contoso는 파일럿 그룹과의 호환성 문제를 해결 한 후에 작업 순서를 실행 하 여 Microsoft 365 Apps for 엔터프라이즈 패키지를 광범위 한 그룹에 배포 합니다.

Contoso는 자동으로 클라우드로부터 장치를 업데이트하도록 선택했기 때문에 구성 관리자에서 프로세스를 관리할 필요가 없습니다. 이러한 장치는 초기 배포에 정의 된 업데이트 채널을 통해 클라우드 기반에서 직접 자동으로 업데이트 됩니다.

엔터프라이즈 설치 및 진행 중인 업데이트 배포 아키텍처에 대 한 Contoso Microsoft 365 앱은 다음과 같습니다.

![Microsoft 365 for enterprise 용 Contoso 배포 인프라](../media/contoso-o365pp/contoso-o365pp-fig1.png)
 
## <a name="next-step"></a>다음 단계

Contoso가 Microsoft 365의 microsoft [Intune을 사용 하 여](contoso-mdm.md) 해당 장치 및 조직 전체에서 실행 하는 앱을 관리 하는 방법을 알아봅니다.

## <a name="see-also"></a>참고 항목

[Microsoft Office 365 ProPlus](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps)

[엔터프라이즈용 Microsoft 365 개요](microsoft-365-overview.md)

[테스트 랩 가이드](m365-enterprise-test-lab-guides.md)
