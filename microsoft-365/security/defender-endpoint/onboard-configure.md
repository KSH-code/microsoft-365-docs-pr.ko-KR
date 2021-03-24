---
title: Microsoft Defender ATP 서비스에 장치 온보딩
description: Windows 10 장치, 서버, 비 Windows 장치를 온보드하고 검색 테스트를 실행하는 방법을 배워야 합니다.
keywords: 온보딩, 끝점 온보딩을 위한 Microsoft Defender, windows atp 온보딩, sccm, 그룹 정책, mdm, 로컬 스크립트, 검색 테스트
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 1deb8a0e00785705937d4cf6de71a030d3d9c971
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51061141"
---
# <a name="onboard-devices-to-the-microsoft-defender-for-endpoint-service"></a>Microsoft Defender for Endpoint 서비스에 장치 온보딩

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

>Endpoint용 Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

지원되는 디바이스를 온보딩하려면 Endpoint 포털의 온보딩 섹션으로 이동해야 합니다. 장치에 따라 적절한 단계를 안내하고 장치에 적합한 관리 및 배포 도구 옵션을 제공합니다. 

일반적으로 디바이스를 서비스에 온보드합니다.

- 장치가 최소 요구 사항을 [충족하는지 확인](minimum-requirements.md)
- 장치에 따라 끝점 포털용 Defender의 온보딩 섹션에 제공된 구성 단계를 따릅니다.
- 장치에 적합한 관리 도구 및 배포 방법 사용
- 검색 테스트를 실행하여 장치가 제대로 온보드 및 서비스에 보고되었는지 확인합니다.

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqr]

## <a name="onboarding-tool-options"></a>온보더링 도구 옵션
다음 표에는 온보드해야 하는 끝점에 따라 사용 가능한 도구가 나열됩니다.

| 끝점     | 도구 옵션                       |
|--------------|------------------------------------------|
| **Windows**  |  [로컬 스크립트(최대 10대의 장치)](configure-endpoints-script.md) <br>  [그룹 정책](configure-endpoints-gp.md) <br>  [Microsoft Endpoint Manager/ 모바일 장치 관리자](configure-endpoints-mdm.md) <br>   [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br> [VDI 스크립트](configure-endpoints-vdi.md)   |
| **macOS**    | [로컬 스크립트](mac-install-manually.md) <br> [Microsoft Endpoint Manager](mac-install-with-intune.md) <br> [JAMF Pro](mac-install-with-jamf.md) <br> [모바일 장치 관리](mac-install-with-other-mdm.md) |
| **Linux Server** | [로컬 스크립트](linux-install-manually.md) <br> [Puppet](linux-install-with-puppet.md) <br> [Ansible](linux-install-with-ansible.md)|
| **iOS**      | [앱 기반](ios-install.md)                                |
| **Android**  | [Microsoft Endpoint Manager](android-intune.md)               | 




## <a name="in-this-section"></a>이 섹션의 내용
항목 | 설명
:---|:---
[이전 버전의 Windows 온보드](onboard-downlevel.md)| 끝점용 Defender에 Windows 7 및 Windows 8.1 장치를 온보딩합니다. 
[Windows 10 장치 온보드](configure-endpoints.md) | 디바이스를 끝점용 Defender 서비스에 보고하려면 장치를 온보딩해야 합니다. 엔터프라이즈에서 장치를 구성하는 데 사용할 수 있는 도구 및 방법에 대해 자세히 알아보습니다.
[서버 온보드](configure-server-endpoints.md) |  Windows Server 2008 R2 SP1, Windows Server 2012 R2, Windows Server 2016, Windows Server(SAC) 버전 1803 이상, Windows Server 2019 이상 및 Windows Server 2019 Core Edition을 Endpoint용 Defender에 온보딩합니다.
[비 Windows 장치 온보드](configure-endpoints-non-windows.md) | Endpoint용 Defender는 Windows가 아닌 플랫폼뿐만 아니라 Windows에 대한 중앙 집중식 보안 운영 환경을 제공합니다. Microsoft Defender 보안 센터에서 지원되는 다양한 OS(운영 체제)에서 경고를 보고 조직의 네트워크를 보다 잘 보호할 수 있습니다. 이 환경은 타사 보안 제품의 센서 데이터를 활용합니다. 
[새로 온보드된 장치에서 검색 테스트 실행](run-detection-test.md) | 새로 온보딩된 장치에서 스크립트를 실행하여 끝점용 Defender 서비스에 제대로 보고하고 있는지 확인합니다.
[프록시 및 인터넷 설정 구성](configure-proxy-internet.md)| 프록시 및 인터넷 연결 설정을 구성하여 Endpoint 클라우드 서비스용 Defender와 통신할 수 있습니다.
[온보더링 문제 해결](troubleshoot-onboarding.md) | 온보더링 중에 발생할 수 있는 문제를 해결합니다.

>Endpoint용 Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)
