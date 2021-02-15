---
title: 탐지된 위협 검토 및 조치 수행
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: Windows 10 장치에서 Microsoft Defender 바이러스 백신이 감지한 위협을 검토하고 관리하는 방법을 알아보십시오.
ms.openlocfilehash: 41465cb81850415a7b490b6af7f0ec66c724ca68
ms.sourcegitcommit: 490a65d32b6d656c661c36a2cc8dda03bf6cba77
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/08/2020
ms.locfileid: "49588520"
---
# <a name="review-detected-threats-and-take-action"></a>탐지된 위협 검토 및 조치 수행

악성 파일 또는 소프트웨어가 감지되는 즉시 Microsoft Defender 바이러스 백신은 해당 파일을 차단하고 실행을 차단합니다. 또한 클라우드 제공 보호가 켜져 있는 경우 새로 감지된 위협이 바이러스 백신 및 맬웨어 방지 엔진에 추가되어 다른 장치와 사용자도 보호됩니다.

Microsoft Defender 바이러스 백신은 다음과 같은 종류의 위협을 감지하고 보호합니다.

- 장치에서 바이러스, 맬웨어 및 웹 기반 위협
- 피싱 시도
- 데이터 도난 시도

IT 전문가/관리자는 Microsoft 365 관리 센터에서 [Intune에](/mem/intune/enrollment/device-enrollment) 등록된 Windows 10 장치에서 위협 감지에 대한 정보를 볼 수 있습니다. 다음과 같은 요약 정보가 표시 됩니다.

- 바이러스 백신 보호가 필요한 장치 수
- 보안 정책을 준수하지 않는 장치 수
- 현재 활성, 완화 또는 해결된 위협 수

위협 감지 및 장치에 대한 특정 정보를 볼 수 있는 몇 가지 옵션이 있습니다.

- Microsoft  <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">365</a>관리 센터의 활성 장치 페이지 이 [문서의 활성](#manage-threat-detections-on-the-active-devices-page) 장치 페이지에서 위협 감지 관리 페이지를 참조하세요.
- Microsoft  <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">365</a>관리 센터의 활성 위협 페이지 이 [문서의 활성 위협 페이지에서](#manage-threat-detections-on-the-active-threats-page) 위협 감지 관리 페이지를 참조하세요.
- Microsoft **Endpoint** <a href="https://go.microsoft.com/fwlink/p/?linkid=2150463" target="_blank">Manager의 바이러스 백신 페이지</a> 이 [문서의 Microsoft Endpoint Manager에서 위협](#manage-threat-detections-in-microsoft-endpoint-manager) 감지 관리 기능을 참조하세요.

자세한 내용은 [Microsoft Defender 바이러스 백신에서 검색된 위협을 참조합니다.](threats-detected-defender-av.md)

## <a name="manage-threat-detections-on-the-active-devices-page"></a>활성 디바이스 페이지에서 위협 **감지 관리**

다음 절차는 Microsoft 365 Business Premium이 있는 고객에게 적용됩니다.

1. Microsoft 365 관리 센터로 이동하여 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 로그인합니다.

2. 탐색 페이지에서 장치   >  **활성 장치를 선택합니다.** 활성 장치 및 보호 상태, 바이러스 백신(AV) 보호 상태, 감지된 활성 위협 수 등의 세부 정보 목록이 표시됩니다.

3. 디바이스를 선택하여 해당 장치 및 사용 가능한 작업에 대한 자세한 내용을 확인합니다. 플라이아웃이 권장 사항 및 사용 가능한 작업(예: 업데이트 **정책,** 업데이트 바이러스 **백신,** 빠른 검사 **실행,** 전체 검사 실행 등)으로 열립니다. 

## <a name="manage-threat-detections-on-the-active-threats-page"></a>활성 위협 페이지에서 위협 **감지** 관리

다음 절차는 Microsoft 365 Business Premium이 있는 고객에게 적용됩니다. [Windows 10 디바이스를](/microsoft-365/business/secure-win-10-pcs) [보호하고 Intune에 등록해야 합니다.](/mem/intune/enrollment/windows-enrollment-methods)

> [!NOTE]
> **Microsoft Defender 바이러스** 백신 카드 및 **활성** 위협 페이지가 단계적으로 롤아웃되고 있으므로 즉시 액세스할 수 없습니다.

1. Microsoft 365 관리 센터로 이동하여 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 로그인합니다.

2. Microsoft **Defender 바이러스 백신** 카드에서 활성 **위협 보기를 선택합니다.** (또는 탐색 창에서 상태 **선택**  >  **바이러스 &** 위협)

3. 활성 위협 **페이지에서** 감지된 위협을 선택하여 해당 위협에 대해 자세히 알아보십시오. 영향을 받는 장치를 포함하여 위협에 대한 세부 정보가 있는 플라이아웃이 열립니다.

4. 플라이아웃에서 업데이트 정책, 업데이트 바이러스 **백신,** 빠른 검사 실행 등의 사용 가능한 작업을 볼 장치를 선택합니다.

## <a name="actions-you-can-take"></a>수행할 수 있는 작업

특정 위협 또는 장치에 대한 세부 정보를 볼 때 권장 사항과 수행할 수 있는 하나 이상의 작업이 표시됩니다. 다음 표에서는 표시될 수 있는 작업에 대해 설명하고 있습니다.<br><br>

| 조치 | 설명 |
|--|--|
| 보호 구성 | 위협 방지 정책을 구성해야 합니다. 정책 구성 페이지로 이동하려면 링크를 선택합니다.<br><br>도움이 필요하신가요? [Microsoft Intune에서 끝점](/mem/intune/protect/endpoint-security-policy)보안 정책을 사용하여 장치 보안 관리를 참조하세요. |
| 업데이트 정책 | 바이러스 백신 및 실시간 보호 정책을 업데이트하거나 구성해야 합니다. 정책 구성 페이지로 이동하려면 링크를 선택합니다.<br><br>도움이 필요하신가요? [Microsoft Intune에서 끝점](/mem/intune/protect/endpoint-security-policy)보안 정책을 사용하여 장치 보안 관리를 참조하세요. |
| 빠른 검사 실행 | 레지스트리 키 및 알려진 Windows 시작 폴더와 같이 맬웨어가 등록될 수 있는 일반적인 위치에 초점을 맞추고 장치에서 빠른 바이러스 백신 검색을 시작합니다. |
| 전체 검사 실행 | 맬웨어가 등록될 수 있는 일반적인 위치와 장치의 모든 파일 및 폴더를 포함하여 디바이스에서 전체 바이러스 백신 검색을 시작합니다. 결과가 Microsoft [Endpoint Manager로 전송됩니다.](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) |
| 바이러스 백신 업데이트 | 장치에 바이러스 백신 [](https://go.microsoft.com/fwlink/?linkid=2149926) 및 맬웨어 방지 보호에 대한 보안 인텔리전스 업데이트를 다운로드해야 합니다. |
| 장치 다시 시작 | 5분 내에 Windows 10 장치를 강제로 다시 시작합니다.<br><br>**중요:** 장치 소유자 또는 사용자에게 다시 시작에 대한 알림을 자동으로 제공하지는 못해, 이로인한 작업의 손실이 있을 수 있습니다. |

## <a name="manage-threat-detections-in-microsoft-endpoint-manager"></a>Microsoft Endpoint Manager에서 위협 감지 관리

Microsoft Endpoint Manager를 사용하여 위협 검색을 관리할 수 있습니다. Windows 10 장치는 [Intune(Microsoft](/mem/intune/enrollment/windows-enrollment-methods) Endpoint Manager의 일부)에 등록해야 합니다.

1. Microsoft Endpoint Manager 관리 센터로 이동하여 <a href="https://go.microsoft.com/fwlink/p/?linkid=2150463" target="_blank">https://endpoint.microsoft.com</a> 로그인합니다.

2. 탐색 창에서 **끝점 보안을 선택합니다.**

3. **관리에서** 바이러스 백신을 **선택합니다.** 요약, **Windows 10의** 불안정한 끝점, **Windows 10** 검색된 맬웨어 등 여러 탭이 표시됩니다.

4. 사용 가능한 탭의 정보를 검토한 다음 필요한 작업을 수행하세요.

예를 들어 장치가 **검색된 Windows 10 맬웨어 탭에 나열되어 있는 경우를 가정해** 보겠습니다. 장치를 선택하면 다시 시작, 빠른 검사, 전체 검사, 동기화 또는 서명 업데이트와 같은 특정 작업을 사용할 **수 있습니다.**  해당 장치에 대한 작업을 선택합니다.

다음 표에서는 Microsoft Endpoint Manager에 표시될 수 있는 작업에 대해 설명하고 있습니다.<br><br>

| 조치 | 설명 |
|--|--|
| 다시 시작 | 5분 내에 Windows 10 장치를 강제로 다시 시작합니다.<br><br>**중요:** 장치 소유자 또는 사용자에게 다시 시작에 대한 알림을 자동으로 제공하지는 못해, 이로인한 작업의 손실이 있을 수 있습니다. |
| 빠른 검사 | 레지스트리 키 및 알려진 Windows 시작 폴더와 같이 맬웨어가 등록될 수 있는 일반적인 위치에 초점을 맞추고 장치에서 빠른 바이러스 백신 검색을 시작합니다. 결과가 Microsoft [Endpoint Manager로 전송됩니다.](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) |
| 전체 검사 | 맬웨어가 등록될 수 있는 일반적인 위치와 장치의 모든 파일 및 폴더를 포함하여 디바이스에서 전체 바이러스 백신 검색을 시작합니다. 결과가 Microsoft [Endpoint Manager로 전송됩니다.](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) |
| 동기화 | Intune(Microsoft Endpoint Manager의 일부)으로 장치를 체크 인해야 합니다. 장치가 체크 인하면 장치에 할당된 보류 중인 작업이나 정책이 장치에서 수신됩니다. |
| 서명 업데이트 | 장치에 바이러스 백신 [](https://go.microsoft.com/fwlink/?linkid=2149926) 및 맬웨어 방지 보호에 대한 보안 인텔리전스 업데이트를 다운로드해야 합니다. |

> [!TIP]
> 자세한 내용은 디바이스에 [대한 원격 작업을 참조하세요.](/mem/intune/protect/endpoint-security-manage-devices#remote-actions-for-devices)

## <a name="how-to-submit-a-file-for-malware-analysis"></a>맬웨어 분석을 위해 파일을 제출하는 방법

누락되거나 잘못 맬웨어로 분류된 파일이 있는 경우 맬웨어 분석을 위해 해당 파일을 Microsoft에 제출할 수 있습니다. 사용자와 IT 관리자는 분석을 위해 파일을 제출할 수 있습니다. [https://www.microsoft.com/wdsi/filesubmission](https://www.microsoft.com/wdsi/filesubmission).를 방문합니다.
