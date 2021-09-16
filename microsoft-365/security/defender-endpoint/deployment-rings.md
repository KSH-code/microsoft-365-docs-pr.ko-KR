---
title: 링에서 끝점용 Microsoft Defender 배포
description: 링에서 끝점용 Microsoft Defender를 배포하는 방법 학습
keywords: 배포, 링, 평가, 파일럿, 내부자 빠른, 내부자 저속, 설치, 온보드, 단계, 배포, 배포, 채택, 구성
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-overview
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a9b7d78893f91242f5570a0df9fcbc3cab55bd4b
ms.sourcegitcommit: 4740e69326eb7f8302eec7bab5bd516d498e4492
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/16/2021
ms.locfileid: "59399301"
---
# <a name="deploy-microsoft-defender-for-endpoint-in-rings"></a>링에서 끝점용 Microsoft Defender 배포

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

링 기반 배포 방법을 사용하여 끝점에 대한 Microsoft Defender 배포를 완료할 수 있습니다.

배포 링은 다음과 같은 시나리오에서 적용할 수 있습니다.

- [새 배포](#new-deployments)
- [기존 배포](#existing-deployments)

## <a name="new-deployments"></a>새 배포

![배포 링의 이미지입니다.](images/deployment-rings.png)

링 기반 접근 방식은 온보드할 끝점 집합을 식별하고 서비스를 더 큰 장치 집합에 배포하기 전에 특정 조건이 충족되는지 확인하는 방법입니다. 각 링에 대한 종료 조건을 정의하고 다음 링으로 이동하기 전에 해당 링이 충족되도록 할 수 있습니다.

링 기반 배포를 채택하면 서비스를 배포하는 동안 발생할 수 있는 잠재적인 문제를 줄일 수 있습니다. 특정 수의 장치를 먼저 파일럿하여 잠재적인 문제를 식별하고 발생할 수 있는 잠재적인 위험을 완화할 수 있습니다.

표 1에서는 사용할 수 있는 배포 링의 예를 제공합니다.

**표 1:**

<br>

****

|배포 링|설명|
|---|---|
|평가|링 1: 파일럿 테스트용 시스템 50개 식별|
|파일럿|링 2: 프로덕션 환경에서 다음 50-100개 끝점 식별|
|전체 배포|링 3: 더 큰 증분으로 나머지 환경에 서비스 롤아웃|
|

### <a name="exit-criteria"></a>종료 조건

이러한 링에 대한 종료 조건의 예는 다음과 같습니다.

- 장치 인벤토리 목록에 장치가 표시됩니다.
- 알림이 대시보드에 표시
- [검색 테스트 실행](run-detection-test.md)
- [디바이스에 대한 시뮬레이션된 공격 실행](attack-simulations.md)

### <a name="evaluate"></a>평가

환경에 있는 소수의 테스트 컴퓨터를 식별하여 서비스에 온보드합니다. 이상적으로 이러한 컴퓨터는 끝점 50개 미만입니다.

### <a name="pilot"></a>파일럿

끝점용 Microsoft Defender는 서비스에 온보딩할 수 있는 다양한 끝점을 지원합니다. 이 링에서 온보드할 여러 장치를 식별하고 정의한 종료 기준에 따라 다음 배포 링으로 진행하기로 결정합니다.

다음 표에는 지원되는 끝점과 장치를 서비스에 온보드하는 데 사용할 수 있는 해당 도구가 표시됩니다.

<br>

****

|끝점|배포 도구|
|---|---|
|**Windows**|[로컬 스크립트(최대 10대의 장치)](configure-endpoints-script.md) <p> **참고:** 프로덕션 환경에 10개 이상의 장치를 배포하려는 경우 그룹 정책 방법이나 아래에 나열된 다른 지원되는 도구를 대신 사용합니다. <p> [그룹 정책](configure-endpoints-gp.md) <p> [Microsoft Endpoint Manager/ 모바일 장치 관리자](configure-endpoints-mdm.md) <p> [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <p> [VDI 스크립트](configure-endpoints-vdi.md) <p> [Azure Defender와 통합](configure-server-endpoints.md#integration-with-azure-defender)|
|**macOS**|[로컬 스크립트](mac-install-manually.md) <p> [Microsoft Endpoint Manager ](mac-install-with-intune.md) <p> [JAMF Pro](mac-install-with-jamf.md) <p> [모바일 장치 관리](mac-install-with-other-mdm.md)|
|**Linux Server**|[로컬 스크립트](linux-install-manually.md) <p> [Puppet](linux-install-with-puppet.md) <p> [Ansible](linux-install-with-ansible.md)|
|**iOS**|[앱 기반](ios-install.md)|
|**Android**|[Microsoft Endpoint Manager ](android-intune.md)|
|

### <a name="full-deployment"></a>전체 배포

이 단계에서 배포 계획 자료를 [사용하여](deployment-strategy.md) 배포를 계획할 수 있습니다.

다음 자료를 사용하여 조직에 가장 적합한 끝점 아키텍처용 Microsoft Defender를 선택합니다.

|**항목**|**설명**|
|:-----|:-----|
|[![Endpoint 배포 전략용 Microsoft Defender의 축소판 이미지입니다.](images/mde-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)<br/> [PDF](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.pdf)  \| [Visio](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.vsdx) | 건축 자료는 다음 아키텍처의 배포를 계획하는 데 도움이 됩니다. <ul><li> 클라우드 네이티브 </li><li> 공동 관리 </li><li> 온-프레미스</li><li>평가 및 로컬 온보딩</li></ul>

## <a name="existing-deployments"></a>기존 배포

### <a name="windows-endpoints"></a>Windows 끝점

Windows 및/Windows 서버의 경우 **SUVP(보안** 업데이트 유효성 검사 프로그램)를 사용하여 미리 테스트할 여러 컴퓨터를 선택합니다(화요일 패치 전).

자세한 내용은 다음을 참조하세요.

- [보안 업데이트 유효성 검사 프로그램](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/what-is-the-security-update-validation-program/ba-p/275767)
- [소프트웨어 업데이트 유효성 검사 프로그램 및 Microsoft 맬웨어 보호 센터 설치 - TwC 대화형 타임라인 4부](https://www.microsoft.com/security/blog/2012/03/28/software-update-validation-program-and-microsoft-malware-protection-center-establishment-twc-interactive-timeline-part-4/)

### <a name="non-windows-endpoints"></a>비 Windows 끝점

macOS 및 Linux에서는 몇 가지 시스템을 사용하며 베타 채널에서 실행할 수 있습니다.

> [!NOTE]
> 빌드를 현재 채널로 만들기 전에 호환성, 성능 및 안정성 문제를 찾을 수 있도록 하나 이상의 보안 관리자와 개발자 한 명 이상입니다.

채널 선택에 따라 장치에 제공되는 업데이트의 유형과 빈도가 결정됩니다. Beta의 장치는 업데이트 및 새 기능을 수신하는 첫 번째 장치로, 나중에 미리 보기 및 마지막으로 현재가 표시됩니다.

![내부자 링의 이미지입니다.](images/insider-rings.png)

새 기능을 미리 보고 초기 피드백을 제공하기 위해서는 엔터프라이즈에서 베타 또는 미리 보기를 사용하도록 일부 장치를 구성하는 것이 좋습니다.

> [!WARNING]
> 초기 설치 후 채널을 전환하려면 제품을 다시 설치해야 합니다. 제품 채널을 전환하려면 기존 패키지를 제거하고 새 채널을 사용하도록 장치를 다시 구성하고 이 문서의 단계에 따라 새 위치에서 패키지를 설치합니다.
