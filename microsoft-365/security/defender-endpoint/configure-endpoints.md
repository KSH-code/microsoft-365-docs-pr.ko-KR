---
title: 장치용 온보더링 Windows 방법
description: 끝점 Windows Microsoft Defender 센서로 센서 데이터를 보낼 수 있도록 장치 온보딩
keywords: 온보딩 Windows 장치, 그룹 정책, 끝점 구성 관리자, 모바일 장치 관리, 로컬 스크립트, gp, sccm, mdm, intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 26f4789ed5c44a2a3380476c78cea67daab84917
ms.sourcegitcommit: be095345257225394674698beb3feeb0696ec86d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/08/2021
ms.locfileid: "60240512"
---
# <a name="onboarding-tools-and-methods-for-windows-devices-in-defender-for-endpoint"></a>Endpoint용 Defender의 Windows 장치용 온보딩 도구 및 방법

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft 365 끝점 DLP(데이터 손실 방지)](/microsoft-365/compliance/endpoint-dlp-learn-about)
- [Microsoft 365 내부자 위험 관리](/microsoft-365/compliance/insider-risk-management)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

끝점용 Defender 서비스가 해당 장치에서 센서 데이터를 얻을 수 있도록 조직의 장치를 구성해야 합니다. 조직에서 장치를 구성하는 데 사용할 수 있는 다양한 방법 및 배포 도구가 있습니다.

일반적으로 온보더링할 Windows 식별한 다음 장치 또는 환경에 적합한 도구를 따르게 됩니다.

![온보더링 도구 및 방법의 이미지](images/onboarding-config-tools.png)

## <a name="endpoint-onboarding-tools"></a>끝점 온보더링 도구
온보 Windows 끝점에 따라 다음 표에 설명된 해당 도구 또는 방법을 사용합니다.

Windows 장치 | 온보더링 도구 또는 방법
:---|:---
|<ul><li> Windows 10</li> <li>Windows 서버 1803 및 2019 및 2022</li> <li>Windows Server 2012 R2 및 2016 <sup> [[1]](#fn1)<sup></li></ul>  |   [로컬 스크립트(최대 10대의 장치)](configure-endpoints-script.md)<br>   [그룹 정책](configure-endpoints-gp.md)<br>   [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br> [Microsoft Endpoint Manager/ 모바일 장치 관리(Intune)](configure-endpoints-mdm.md)<br>    [VDI 스크립트](configure-endpoints-vdi.md) <br><br> **참고:** 로컬 스크립트는 개념 증명에 적합하지만 프로덕션 배포에는 사용되지 않습니다. 프로덕션 배포의 경우 그룹 정책, Microsoft Endpoint Configuration Manager 또는 Intune을 사용하는 것이 좋습니다.
|<ul><li> Windows Server 2008 R2 SP1 </li></ul>| [Microsoft Monitoring Agent(MMA)](onboard-downlevel.md) <br>[이전 버전의 Windows](onboard-downlevel.md) [또는 Azure Defender 온보딩](/azure/security-center/security-center-wdatp) <br><br> **참고:** Microsoft Monitoring Agent Azure Log Analytics 에이전트가 됩니다. 자세한 내용은 Log Analytics 에이전트 [개요를 참조하세요.](/azure/azure-monitor/platform/log-analytics-agent)  
|<ul><li> Windows 7 SP1 </li> <li>  Windows 7 SP1 Pro </li> <li>  Windows 8.1 Pro </li> <li> Windows 8.1 Enterprise</li></ul>  | [Microsoft Monitoring Agent(MMA)](onboard-downlevel.md) <br><br> **참고:** Microsoft Monitoring Agent Azure Log Analytics 에이전트가 됩니다. 자세한 내용은 Log Analytics 에이전트 [개요를 참조하세요.](/azure/azure-monitor/platform/log-analytics-agent)



(<a id="fn1">1</a>) Windows Server 2016 Windows Server 2012 R2는 온보드 서버의 지침을 사용하여 Windows [합니다.](configure-server-endpoints.md#windows-server-2012-r2-and-windows-server-2016)

항목|설명
:---|:---
[그룹 정책을 사용하여 장치 온보딩](configure-endpoints-gp.md)|그룹 정책을 사용하여 디바이스에 구성 패키지를 배포합니다.
[Microsoft Endpoint Configuration Manager를 사용하여 장치 온보딩](configure-endpoints-sccm.md)|Microsoft Endpoint Manager(현재 분기) 버전 1606 또는 Microsoft Endpoint Manager(현재 분기) 버전 1602 이전 버전을 사용하여 디바이스에 구성 패키지를 배포할 수 있습니다.
[모바일 장치 관리 도구를 사용하여 장치 온보딩](configure-endpoints-mdm.md)|모바일 장치 관리 도구 또는 Microsoft Intune 구성 패키지를 배포할 수 있습니다.
[로컬 스크립트를 사용하여 장치 온보딩](configure-endpoints-script.md)|로컬 스크립트를 사용하여 끝점에서 구성 패키지를 배포하는 방법을 학습합니다.
[비영구 VDI(가상 데스크톱 인프라) 장치 온보딩](configure-endpoints-vdi.md)|구성 패키지를 사용하여 VDI 디바이스를 구성하는 방법을 학습합니다.

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configureendpoints-belowfoldlink)


장치를 온보드한 후 검색 테스트를 실행하여 장치가 서비스에 제대로 온보드되었는지 확인할 수 있습니다. 자세한 내용은 새로 온보딩된 끝점 디바이스용 Microsoft Defender에서 검색 테스트 [실행을 참조하세요.](run-detection-test.md)