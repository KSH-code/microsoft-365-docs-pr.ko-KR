---
title: 자동화된 조사를 사용하여 위협 조사 및 수정
description: 끝점용 Microsoft Defender의 자동화된 조사 흐름을 이해합니다.
keywords: 자동화, 조사, 검색, 끝점용 Microsoft Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: JoeDavies-MSFT
ms.author: josephd
ms.date: 02/02/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: how-to
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.custom: AIR
ms.openlocfilehash: 7b1ce14e1ec01041ea9b3a298f4f794978054e5f
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60193054"
---
# <a name="overview-of-automated-investigations"></a>자동 조사 개요

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

작동 방법을 보고 싶나요? 다음 비디오를 시청합니다.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bOeh]

자동화된 조사의 기술은 다양한 검사 알고리즘을 사용하며 보안 분석가가 사용하는 프로세스를 기반으로 합니다. AIR 기능은 경고를 검사하고 위반을 해결하기 위해 즉각적인 조치를 취하도록 고안되었습니다. AIR 기능은 경고 볼륨을 크게 줄여 보안 운영이 보다 정교한 위협 및 기타 고가치 이니셔티브에 집중할 수 있도록 합니다. 보류 중인지 완료 여부에 따라 모든 수정 작업은 관리 센터에서 [추적됩니다.](auto-investigation-action-center.md) 작업 센터에서 보류 중인 작업이 승인되거나 거부될 수 있으며, 필요한 경우 완료된 작업을 실행하지 않습니다.

이 문서에서는 AIR에 대한 개요를 제공하며 다음 단계 및 추가 리소스에 대한 링크를 제공합니다.

> [!TIP]
> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-automated-investigations-abovefoldlink)

## <a name="how-the-automated-investigation-starts"></a>자동화된 조사 시작 방법

경고가 트리거되거나 보안 운영자가 조사를 시작할 때 자동화된 조사가 시작될 수 있습니다.

<br>

****

|상황|발생 작업|
|---|---|
|경고가 트리거됩니다.|일반적으로 경고가 트리거되면 자동화된 [](review-alerts.md) 조사가 시작되고 [인시던트가](view-incidents-queue.md) 생성됩니다. 예를 들어 악성 파일이 장치에 있는 경우를 가정해 보겠습니다. 해당 파일이 검색되면 경고가 트리거되고 인시던트가 만들어집니다. 자동화된 조사 프로세스가 디바이스에서 시작됩니다. 다른 장치에서 동일한 파일로 인시던트가 생성되는 다른 경고는 관련 인시던트 및 자동화된 조사에 추가됩니다.|
|조사가 수동으로 시작|보안 운영 팀에서 자동화된 조사를 수동으로 시작할 수 있습니다. 예를 들어 보안 운영자가 장치 목록을 검토하고 장치에 높은 위험 수준이 있는 것으로 표시하는 경우를 가정해 보겠습니다. 보안 운영자는 목록에서 디바이스를 선택하여 플라이아웃을 연 다음 자동화된 조사 **시작을 선택할 수 있습니다.**|
|

## <a name="how-an-automated-investigation-expands-its-scope"></a>자동화된 조사가 범위를 확장하는 방법

조사가 실행되는 동안 장치에서 생성된 다른 모든 경고는 해당 조사가 완료될 때까지 진행 중인 자동화된 조사에 추가됩니다. 또한 다른 장치에서 동일한 위협이 있는 경우 해당 장치가 조사에 추가됩니다.

다른 디바이스에서 인출된 엔터티가 볼 수 있는 경우 자동화된 조사 프로세스는 해당 장치를 포함하기 위해 해당 범위를 확장하고 해당 장치에서 일반 보안 플레이북이 시작됩니다. 동일한 엔터티에서 이 확장 프로세스 중에 10개 이상의 장치가 발견되는 경우 해당 확장 작업을 수행하려면 승인이 필요하며 보류 중인 작업 **탭에** 표시됩니다.

## <a name="how-threats-are-remediated"></a>위협을 수정하는 방법

경고가 트리거되고 자동화된 조사가 실행되면 조사된 각 증거 조각에 대한 판결이 생성됩니다. 판정은 다음이 될 수 있습니다.

- *악성*;
- *의심스러운 ;* 또는
- *위협이 없습니다.*

결과가 도달하면 자동화된 조사를 통해 하나 이상의 수정 작업이 수행될 수 있습니다. 수정 작업의 예로는 파일을 검지로 보내기, 서비스 중지, 예약된 작업 제거 등입니다. 자세한 내용은 재구성 [작업 을 참조합니다.](manage-auto-investigation.md#remediation-actions)

조직에 설정된 [](automation-levels.md) 자동화 수준 및 기타 보안 설정에 따라 수정 작업은 자동으로 또는 보안 운영 팀의 승인 시에만 발생할 수 있습니다. 자동 수정에 영향을 줄 수 있는 추가 보안 설정에는 잠재적으로 원치 않는 응용 프로그램(PUA)으로부터의 [보호가](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus) 포함됩니다.

보류 중인지 완료 여부에 따라 모든 수정 작업은 관리 센터에서 [추적됩니다.](auto-investigation-action-center.md) 필요한 경우 보안 운영 팀에서 수정 작업을 실행 취소할 수 있습니다. 자세한 내용은 자동화된 조사 후 재구성 작업 검토 및 [승인을 참조합니다.](/microsoft-365/security/defender-endpoint/manage-auto-investigation)

> [!TIP]
> 보안 센터의 새로운 통합 조사 Microsoft 365 확인 합니다. 자세한 내용은 [(NEW!)를 참조하세요. 통합 조사 페이지.](/microsoft-365/security/defender/m365d-autoir-results#new-unified-investigation-page)

## <a name="requirements-for-air"></a>AIR에 대한 요구 사항

조직에 끝점용 Defender가 있어야 합니다(끝점용 [Microsoft Defender에 대한 최소](minimum-requirements.md)요구 사항 참조).

현재 AIR은 다음 OS 버전만 지원됩니다.

- Windows Server 2019
- Windows Server 2022
- Windows 10 버전 1709(OS 빌드 [16299.1085(KB4493441)](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441)이상
- Windows 10 버전 1803(OS 빌드 [17134.704(KB4493464)](https://support.microsoft.com/help/4493464/windows-10-update-kb4493464)이상
- Windows 10 버전 [1803](/windows/release-information/status-windows-10-1809-and-windows-server-2019) 이상

## <a name="next-steps"></a>다음 단계

- [자동화 수준에 대해 자세히 알아보시다](automation-levels.md)
- [대화형 가이드를 참조하세요. Endpoint용 Microsoft Defender로 위협 조사 및 수정](https://aka.ms/MDATP-IR-Interactive-Guide)
- [끝점용 Microsoft Defender에서 자동화된 조사 및 수정 기능 구성](configure-automated-investigations-remediation.md)

## <a name="see-also"></a>참고 항목

- [PUA 보호](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)
- [Microsoft Defender에서 자동화된 조사 및 Office 365](/microsoft-365/security/office-365-security/office-365-air)
- [Microsoft 365 Defender의 자동 조사 및 응답](/microsoft-365/security/defender/mtp-autoir)
