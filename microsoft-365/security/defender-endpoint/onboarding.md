---
title: 엔드포인트용 Microsoft Defender 서비스에 온보딩
description: 끝점을 Microsoft Defender for Endpoint Service에 온보딩하는 방법 학습
keywords: 끝점용 Microsoft Defender, 온보딩, 배포
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ffc1e8b7872f399a03e09b8f6b2b0f65b4ed3eac
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60205274"
---
# <a name="onboard-to-the-microsoft-defender-for-endpoint-service"></a>엔드포인트용 Microsoft Defender 서비스에 온보딩

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

끝점용 Microsoft Defender 배포의 다양한 단계와 솔루션 내에서 기능을 구성하는 방법에 대해 자세히 알아보십시오.

끝점용 Defender 배포는 3단계 프로세스입니다.

|[![배포 단계 - 준비.](images/phase-diagrams/prepare.png)](prepare-deployment.md) <br> [1 단계: 준비](prepare-deployment.md)|[![배포 단계 - 설정](images/phase-diagrams/setup.png)](production-deployment.md) <br> [2 단계: 설정](production-deployment.md)|![배포 단계 - 온보드](images/phase-diagrams/onboard.png) <br> 3 단계: 온보딩|
|---|---|---|
|||*여기 있습니다!*|

현재 온보더링 단계에 있습니다.

끝점용 Defender를 배포하는 데 필요한 단계는 다음 단계입니다.

- 1단계: 서비스에 끝점 온보드
- 2단계: 기능 구성

## <a name="step-1-onboard-endpoints-using-any-of-the-supported-management-tools"></a>1단계: 지원되는 관리 도구를 사용하여 끝점 온보드

배포 [계획 항목에서는](deployment-strategy.md) 끝점용 Defender를 배포하는 데 필요한 일반적인 단계를 간략하게 설명합니다.

이 비디오를 시청하여 온보더링 프로세스에 대한 간략한 개요를 알아보고 사용 가능한 도구 및 방법에 대해 자세히 알아보습니다.


> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqr]

아키텍처를 식별한 후 사용할 배포 방법을 결정해야 합니다. 선택한 배포 도구는 끝점을 서비스에 온보드하는 방법에 영향을 미치게 됩니다.

### <a name="onboarding-tool-options"></a>온보더링 도구 옵션

다음 표에는 온보드해야 하는 끝점에 따라 사용 가능한 도구가 나열됩니다.

|끝점|도구 옵션|
|---|---|
|**Windows**|[로컬 스크립트(최대 10대의 장치)](configure-endpoints-script.md) <br>  [그룹 정책](configure-endpoints-gp.md) <br>  [Microsoft Endpoint Manager/ 모바일 장치 관리자](configure-endpoints-mdm.md) <br> [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br> [VDI 스크립트](configure-endpoints-vdi.md) <br> [Azure Defender와 통합](configure-server-endpoints.md#integration-with-azure-defender)|
|**macOS**|[로컬 스크립트](mac-install-manually.md) <br> [Microsoft Endpoint Manager ](mac-install-with-intune.md) <br> [JAMF Pro](mac-install-with-jamf.md) <br> [모바일 장치 관리](mac-install-with-other-mdm.md)|
|**Linux Server**|[로컬 스크립트](linux-install-manually.md) <br> [Puppet](linux-install-with-puppet.md) <br> [Ansible](linux-install-with-ansible.md)|
|**iOS**|[앱 기반](ios-install.md)|
|**Android**|[Microsoft Endpoint Manager ](android-intune.md)|

## <a name="step-2-configure-capabilities"></a>2단계: 기능 구성

끝점을 온보드한 후 끝점 감지 및 응답, 차세대 보호, 공격 표면 감소와 같은 다양한 기능을 구성합니다.

## <a name="example-deployments"></a>배포 예

이 배포 가이드에서는 두 배포 도구를 사용하여 끝점을 온보드하고 기능을 구성하는 방법을 안내합니다.

예제 배포의 도구는 다음과 같습니다.

- [Microsoft Endpoint Configuration Manager를 사용하여 온보딩](onboarding-endpoint-configuration-manager.md)
- [Microsoft Endpoint Manager를 사용하여 온보딩](onboarding-endpoint-manager.md)

위에서 언급한 배포 도구를 사용하여 끝점에 대해 다음 Defender 기능을 구성하는 방법을 안내합니다.

- 끝점 검색 및 응답 구성
- 차세대 보호 구성
- 공격 표면 감소 구성

## <a name="related-topics"></a>관련 항목

- [Microsoft Endpoint Configuration Manager를 사용하여 온보딩](onboarding-endpoint-configuration-manager.md)
- [Microsoft Endpoint Manager를 사용하여 온보딩](onboarding-endpoint-manager.md)
- [Microsoft 365 E5에서 안전한 문서](../office-365-security/safe-docs.md)
