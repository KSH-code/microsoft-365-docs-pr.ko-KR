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
description: Windows 10 장치에서 Microsoft Defender 바이러스 백신이 감지한 위협을 검토 하 고 관리 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: ffdf5cffb50d6145d6059233e0850839f4dfb582
ms.sourcegitcommit: 26b35012c42fef935d6c4a6509dde6c22a9b922a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2020
ms.locfileid: "49385243"
---
# <a name="review-detected-threats-and-take-action"></a>탐지된 위협 검토 및 조치 수행

악성 파일 또는 소프트웨어가 검색 되는 즉시 Microsoft Defender 바이러스 백신은이를 차단 하 고 실행 되지 않도록 합니다. 또한 클라우드에서 전달 된 보호가 설정 되어 있으면 다른 장치 및 사용자도 보호 되도록 새롭게 검색 된 위협이 바이러스 백신 및 맬웨어 방지 엔진에 추가 됩니다.

Microsoft Defender 바이러스 백신은 다음과 같은 종류의 위협을 감지 하 고 보호 합니다.

- 장치에 대 한 바이러스, 맬웨어 및 웹 기반 위협
- 피싱 시도
- 데이터 도난 시도

IT 전문가/관리자는 Microsoft 365 관리 센터의 [Intune에 등록 되어 있는 Windows 10 장치](/mem/intune/enrollment/device-enrollment) 에서 위협 감지에 대 한 정보를 확인할 수 있습니다. 다음과 같은 요약 정보가 표시 됩니다.

- 바이러스 백신 보호가 필요한 장치 수
- 보안 정책을 준수 하지 않는 장치 수
- 현재 활성, 완화 또는 해결 된 위협의 수

위협 감지 및 장치에 대 한 특정 정보를 보려면 다음과 같은 여러 옵션을 사용할 수 있습니다.

- <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 관리 센터</a>의 **활성 장치** 페이지 이 문서의 [활성 장치 페이지에서 위협 감지 관리](#manage-threat-detections-on-the-active-devices-page) 를 참조 하세요.
- <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 관리 센터</a>의 **활성 위협** 페이지입니다. 이 문서의 [활성 위협 페이지에서 위협 검색 관리를](#manage-threat-detections-on-the-active-threats-page) 참조 하세요.
- <a href="https://endpoint.microsoft.com" target="_blank">Microsoft Endpoint Manager</a>의 **바이러스 검사** 페이지입니다. 이 문서의 [Microsoft Endpoint Manager에서 위협 검색 관리를](#manage-threat-detections-in-microsoft-endpoint-manager) 참조 하세요.

자세한 내용은 [Microsoft Defender Antivirus에서 검색 하는 위협](threats-detected-defender-av.md)항목을 참조 하십시오.

## <a name="manage-threat-detections-on-the-active-devices-page"></a>**활성 장치** 페이지에서 위협 감지 관리

다음 절차는 Microsoft 365 Business Premium이 있는 고객에 게 적용 됩니다.

1. Microsoft 365 관리 센터로 이동 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 하 여 로그인 합니다.

2. 탐색 페이지에서 **장치**  >  **활성 장치** 를 선택 합니다. 활성 장치 및 세부 정보 목록 (보호 상태, 바이러스 검사 (AV) 보호 상태, 검색 된 활성 위협의 수)을 확인할 수 있습니다.

3. 장치를 선택 하 여 해당 장치 및 사용 가능한 작업에 대 한 자세한 정보를 확인 합니다. **업데이트 정책**, **업데이트 바이러스** 검사, **빠른 검색** 실행, **전체 검색 실행** 등 권장 사항 및 사용 가능한 작업을 포함 하는 플라이 아웃이 열립니다.

## <a name="manage-threat-detections-on-the-active-threats-page"></a>**활성 위협** 페이지에서 위협 감지 관리

다음 절차는 Microsoft 365 Business Premium이 있는 고객에 게 적용 됩니다. [Windows 10 장치](/microsoft-365/business/secure-win-10-pcs) 는 [Intune에서](/mem/intune/enrollment/windows-enrollment-methods)보호 되 고 등록 해야 합니다.

> [!NOTE]
> **Microsoft Defender 바이러스 백신** 카드 및 **활성 위협** 페이지는 단계별로 롤아웃 되므로 즉시 액세스 하지 못할 수 있습니다.

1. Microsoft 365 관리 센터로 이동 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 하 여 로그인 합니다.

2. **Microsoft Defender 바이러스 백신** 카드에서 **활성 위협 보기** 를 선택 합니다. 또는 탐색 창에서 **상태**  >  를 선택 합니다. **바이러스 백신 & 위협**

3. **활성 위협** 페이지에서 검색 된 위협을 선택 하 여 자세한 내용을 확인 합니다. 영향을 받는 장치를 포함 하 여 해당 위협에 대 한 세부 정보가 포함 된 플라이 아웃이 열립니다.

4. 플라이 아웃에서 장치를 선택 하 여 **업데이트 정책**, **업데이트 바이러스 검사**, **빠른 검사 실행** 등 사용 가능한 작업을 볼 수 있습니다.

## <a name="actions-you-can-take"></a>수행할 수 있는 작업

특정 위협 또는 장치에 대 한 세부 정보를 볼 때 권장 사항 및 수행할 수 있는 하나 이상의 작업이 표시 됩니다. 다음 표에서는 사용자가 볼 수 있는 작업에 대해 설명 합니다.<br><br>

| 조치 | 설명 |
|--|--|
| 보호 구성 | 위협 보호 정책을 구성 해야 합니다. 링크를 선택 하 여 정책 구성 페이지로 이동 합니다.<br><br>도움이 필요하신가요? [Microsoft Intune에서 끝점 보안 정책을 사용 하 여 장치 보안 관리](/mem/intune/protect/endpoint-security-policy)를 참조 하세요. |
| 정책 업데이트 | 바이러스 백신 및 실시간 보호 정책을 업데이트 하거나 구성 해야 합니다. 링크를 선택 하 여 정책 구성 페이지로 이동 합니다.<br><br>도움이 필요하신가요? [Microsoft Intune에서 끝점 보안 정책을 사용 하 여 장치 보안 관리](/mem/intune/protect/endpoint-security-policy)를 참조 하세요. |
| 빠른 검색 실행 | 레지스트리 키 및 알려진 Windows startup 폴더와 같이 맬웨어를 등록할 수 있는 일반적인 위치에 초점을 맞추어 장치에서 빠른 바이러스 검사를 시작 합니다. |
| 전체 검색 실행 | 맬웨어를 등록할 수 있는 일반적인 위치에 초점을 맞추어 장치에서 전체 바이러스 백신 검사를 시작 하 고 장치의 모든 파일 및 폴더를 포함 합니다. 결과가 [Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)로 전송 됩니다. |
| 바이러스 백신 업데이트 | 장치에서 바이러스 백신 및 맬웨어 방지 보호에 대 한 [보안 인텔리전스 업데이트](https://go.microsoft.com/fwlink/?linkid=2149926) 를 받아야 합니다. |
| 장치 다시 시작 | 5 분 내에 Windows 10 장치를 강제로 다시 시작 합니다.<br><br>**중요:** 장치 소유자 또는 사용자에 게 자동으로 다시 시작 알림이 제공 되지 않으며 저장 되지 않은 작업이 손실 될 수 있습니다. |

## <a name="manage-threat-detections-in-microsoft-endpoint-manager"></a>Microsoft Endpoint Manager에서 위협 감지 관리

Microsoft Endpoint Manager를 사용 하 여 위협 감지를 관리할 수 있습니다. Windows 10 장치는 Intune (Microsoft Endpoint Manager의 일부) [에서 등록](/mem/intune/enrollment/windows-enrollment-methods) 해야 합니다.

1. Microsoft Endpoint Manager 관리 센터로 이동 <a href="https://endpoint.microsoft.com" target="_blank">https://endpoint.microsoft.com</a> 하 여 로그인 합니다.

2. 탐색 창에서 **끝점 보안** 을 선택 합니다.

3. **관리** 에서 **바이러스 검사** 를 선택 합니다. **요약**, **windows 10 비정상 끝점** 및 **Windows 10 검색 된 맬웨어** 같은 여러 탭이 표시 됩니다.

4. 사용 가능한 탭에서 정보를 검토 하 고 필요한 작업을 수행 합니다.

예를 들어 장치가 **Windows 10 검색 된 맬웨어** 탭에 나열 되어 있다고 가정 합니다. 장치를 선택 하면 **다시 시작**, **빠른 검색**, **전체 검색**, **동기화** 또는 **업데이트 서명** 등의 특정 작업을 사용할 수 있습니다. 해당 장치에 대 한 작업을 선택 합니다.

다음 표에서는 Microsoft Endpoint Manager에 표시 될 수 있는 작업에 대해 설명 합니다.<br><br>

| 조치 | 설명 |
|--|--|
| 다시 시작 | 5 분 내에 Windows 10 장치를 강제로 다시 시작 합니다.<br><br>**중요:** 장치 소유자 또는 사용자에 게 자동으로 다시 시작 알림이 제공 되지 않으며 저장 되지 않은 작업이 손실 될 수 있습니다. |
| 빠른 검색 | 레지스트리 키 및 알려진 Windows startup 폴더와 같이 맬웨어를 등록할 수 있는 일반적인 위치에 초점을 맞추어 장치에서 빠른 바이러스 검사를 시작 합니다. 결과가 [Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)로 전송 됩니다. |
| 전체 검색 | 맬웨어를 등록할 수 있는 일반적인 위치에 초점을 맞추어 장치에서 전체 바이러스 백신 검사를 시작 하 고 장치의 모든 파일 및 폴더를 포함 합니다. 결과가 [Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)로 전송 됩니다. |
| 동기화 | Intune을 사용 하 여 체크 인 하는 장치가 필요 합니다 (Microsoft Endpoint Manager의 일부). 장치가 체크 인 되 면 장치에 할당 된 보류 중인 작업 또는 정책이 수신 됩니다. |
| 서명 업데이트 | 장치에서 바이러스 백신 및 맬웨어 방지 보호에 대 한 [보안 인텔리전스 업데이트](https://go.microsoft.com/fwlink/?linkid=2149926) 를 받아야 합니다. |

> [!TIP]
> 자세한 내용은 [장치에 대 한 원격 작업](/mem/intune/protect/endpoint-security-manage-devices#remote-actions-for-devices)을 참조 하세요.

## <a name="how-to-submit-a-file-for-malware-analysis"></a>맬웨어 분석을 위해 파일을 제출 하는 방법

누락 된 것으로 생각 되는 파일이 있거나 지워지는으로 분류 된 경우 맬웨어 분석을 위해 해당 파일을 Microsoft에 제출할 수 있습니다. 사용자 및 IT 관리자는 분석을 위해 파일을 제출할 수 있습니다. [https://www.microsoft.com/wdsi/filesubmission](https://www.microsoft.com/wdsi/filesubmission)를 방문 합니다.
