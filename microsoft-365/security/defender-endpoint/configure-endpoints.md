---
title: Windows 10 장치용 온보딩 도구 및 방법
description: 끝점 Windows 10 센서로 센서 데이터를 보낼 수 있도록 장치 온보딩
keywords: 온보딩 Windows 10 장치, 그룹 정책, 끝점 구성 관리자, 모바일 장치 관리, 로컬 스크립트, gp, sccm, mdm, intune
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
ms.openlocfilehash: 389318ec86b1464b905be35f7de67e5037c94ad3
ms.sourcegitcommit: 87d994407fb69a747239b8589ad11ddf9b47e527
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2021
ms.locfileid: "53596137"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices-in-defender-for-endpoint"></a>Endpoint용 Defender의 Windows 10 장치용 온보딩 도구 및 방법

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft 365 끝점 DLP(데이터 손실 방지)](/microsoft-365/compliance/endpoint-dlp-learn-about)
- [Microsoft 365 내부자 위험 관리](/microsoft-365/compliance/insider-risk-management)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

끝점용 Defender 서비스가 해당 장치에서 센서 데이터를 얻을 수 있도록 조직의 장치를 구성해야 합니다. 조직에서 장치를 구성하는 데 사용할 수 있는 다양한 방법 및 배포 도구가 있습니다.

다음과 같은 배포 도구 및 방법이 지원됩니다.

- 그룹 정책
- Microsoft Endpoint Configuration Manager
- 모바일 장치 관리(Microsoft Intune)
- 로컬 스크립트

## <a name="in-this-section"></a>이 섹션의 내용

항목|설명
:---|:---
[그룹 정책을 Windows 10 장치 온보드](configure-endpoints-gp.md)|그룹 정책을 사용하여 디바이스에 구성 패키지를 배포합니다.
[Windows 사용하여 장치 온보드 Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)|Microsoft Endpoint Manager(현재 분기) 버전 1606 또는 Microsoft Endpoint Manager(현재 분기) 버전 1602 이전 버전을 사용하여 디바이스에 구성 패키지를 배포할 수 있습니다.
[모바일 장치 관리 도구를 사용하여 Windows 10 장치 온보딩](configure-endpoints-mdm.md)|모바일 장치 관리 도구 또는 Microsoft Intune 구성 패키지를 배포할 수 있습니다.
[로컬 스크립트를 사용하여 Windows 10 장치 온보딩](configure-endpoints-script.md)|로컬 스크립트를 사용하여 끝점에서 구성 패키지를 배포하는 방법을 학습합니다.
[비영구 VDI(가상 데스크톱 인프라) 장치 온보딩](configure-endpoints-vdi.md)|구성 패키지를 사용하여 VDI 디바이스를 구성하는 방법을 학습합니다.

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpoints-belowfoldlink)
