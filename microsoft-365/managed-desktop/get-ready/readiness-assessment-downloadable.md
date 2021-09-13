---
title: 다운로드 가능한 준비 평가 검사
description: 필요한 끝점을 포함하여 장치 및 네트워크 설정 확인
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: ba233cf780ad428a9ecfdb6c4a3466b4ec4282da
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59215555"
---
# <a name="downloadable-readiness-assessment-checker"></a>다운로드 가능한 준비 평가 검사

장치와 함께 Microsoft Managed Desktop 하드웨어 및 설정에 대한 특정 요구 사항을 충족해야 합니다. 또한 각 장치는 주요 끝점에 도달할 수 있어야 합니다. 이 도구를 다운로드하여 실행하여 HTML 보고서를 다운로드하고 결과를 본 다음 조치를 취합니다. 도구 및 지원 파일을 다운로드한 다음 등록하려는 각 장치에서 수동으로 실행해야 Microsoft Managed Desktop.

각 검사에 대해 도구는 세 가지 결과 중 하나를 보고합니다.


|결과  |의미  |
|---------|---------|
|준비     | 등록을 완료하기 전에 필요한 작업은 없습니다.        |
|권고    | 등록과 사용자에 대해 최상의 환경을 제공하려면 도구의 단계를 따르세요. *등록을* 완료할 수 있지만 첫 번째 장치를 배포하기 전에 이러한 문제를 해결해야 합니다.        |
|준비되지 않음 | *이러한 문제를* 해결하지 않는 경우 등록이 실패합니다. 도구의 단계에 따라 문제를 해결합니다.        |

## <a name="obtain-the-checker"></a>검사기 얻기

에서 .zip 파일을 https://aka.ms/mmddratoolv0 다운로드합니다.

> [!NOTE]
> 도구를 실행하는 사용자에게는 도구를 실행 중인 디바이스에 대한 로컬 관리자 권한이 있어야 합니다.

 그런 다음 다음 단계를 수행하여 도구를 실행합니다.

1. 다운로드한 .zip 파일을 확인하려는 각 디바이스에 복사합니다.
2. 압축된 다운로드에서 모든 파일을 추출합니다.
3. 를 **Microsoft.MMD.DeviceReadinessAssessmentTool.exe.**
4. 사용자 액세스 제어 프롬프트가 나타나면 예를 **선택합니다.** 이 도구가 실행되어 기본 브라우저에서 보고서를 여는 경우

또한 공유 위치에 .zip 다운로드 및 추출하고, 각  장치에서Microsoft.MMD.DeviceReadinessAssessmentTool.exe액세스한 다음 로컬로 실행할 수도 있습니다.


## <a name="checks"></a>검사

다운로드 가능한 도구는 이러한 장치 및 네트워크 관련 항목을 확인합니다.

### <a name="hardware"></a>하드웨어

디바이스에서 작동하려면 특정 하드웨어 요구 사항을 충족해야 Microsoft Managed Desktop. 자세한 내용은 장치 요구 [사항을 참조하세요.](../service-description/device-list.md)

장치가 검사에 실패하면 장치와 호환되지 Microsoft Managed Desktop.

### <a name="network-endpoints"></a>네트워크 끝점

디바이스는 여러 주요 [](network.md) 끝점에 도달하여 여러 개의 주요 끝점에 연결하여 작업할 Microsoft Managed Desktop.

도구에서 준비되지  않은 결과를 보고하는 경우 자세한 보고서를 참조하여 도달할 수 없는 끝점을 찾아야 합니다. 그런 다음 방화벽 또는 기타 네트워크 설정을 조정하여 해당 끝점에 도달할 수 있도록 합니다.

### <a name="other-settings"></a>기타 설정

#### <a name="enterprise-wi-fi-profiles"></a>Enterprise Wi-Fi 프로필 설정

권고 **결과는** 인증서 및 프로필이 제대로 작동해야 하는 일부 Wi-Fi 프로필을 사용 중이란 의미입니다. 자세한 내용은 인증서 배포 및 [Wi-Fi/VPN 프로필을 참조하세요.](certs-wifi-lan.md#deploy-certificates-and-wi-fivpn-profile)

#### <a name="lan-profiles"></a>LAN 프로필

권고 **결과는** 인증서 및 프로필이 제대로 작동해야 하는 란이 있는 것입니다. 자세한 내용은 [Prepare certificates and network profiles for Microsoft Managed Desktop.](certs-wifi-lan.md)

#### <a name="vpn-profiles"></a>VPN 프로필

권고 **결과는** VPN(가상 사설망)을 사용 중이란 의미입니다. 인증서와 통합된 인증서를 배포하는 VPN 프로필을 Microsoft Intune. 자세한 내용은 [Prepare certificates and network profiles for Microsoft Managed Desktop.](certs-wifi-lan.md)

#### <a name="mapped-drives"></a>매핑된 드라이브

권고 **결과는** 일부 매핑된 드라이브가 있지만 권장되지 않음을 의미합니다. 자세한 내용은 에 대해 매핑된 드라이브 [준비를 Microsoft Managed Desktop.](mapped-drives.md)

#### <a name="print-queues"></a>인쇄 큐

권고 **결과는** 일부 미해결 인쇄 큐가 있는 것으로, 권장되지 않습니다. 한 가지 해결 방법은 클라우드 인쇄를 사용하는 것입니다. 자세한 내용은 [Prepare printing resources for Microsoft Managed Desktop.](printing.md)

#### <a name="proxies"></a>Proxies

권고 **결과는** 사용 중 프록시 서버가 있는 것입니다. 자세한 내용은 에 [대한 네트워크 구성을 Microsoft Managed Desktop.](network.md)

