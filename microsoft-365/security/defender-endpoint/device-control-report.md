---
title: 장치 제어를 사용하여 조직의 데이터 보호
description: 장치 제어 보고서를 통해 조직의 데이터 보안을 모니터링합니다.
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.author: deniseb
author: denisebmsft
ms.reviewer: dansimp
ms.topic: article
manager: dansimp
audience: ITPro
ms.technology: mde
ms.openlocfilehash: fb61525456c01f402bebc2eb0b9934d8f8880fee
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59222826"
---
# <a name="protect-your-organizations-data-with-device-control"></a>장치 제어를 사용하여 조직의 데이터 보호

**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Microsoft Defender for Endpoint 장치 컨트롤은 이동식 저장 장치 및 USB 드라이브 사용과 같은 조직의 장치에서 미디어 사용을 모니터링하고 제어하여 데이터 손실을 방지합니다.

장치 제어 보고서를 사용하여 미디어 사용과 관련된 이벤트를 볼 수 있습니다. 예:

- **감사 이벤트:** 외부 미디어가 연결될 때 발생하는 감사 이벤트 수를 보여줍니다.
- **정책 이벤트:** 장치 제어 정책이 트리거될 때 발생하는 정책 이벤트 수를 보여줍니다.

> [!NOTE]
> 미디어 사용을 추적하기 위한 감사 이벤트는 기본적으로 끝점용 Microsoft Defender에 온보딩된 장치에 대해 사용하도록 설정됩니다.

## <a name="understanding-the-audit-events"></a>감사 이벤트 이해

감사 이벤트는 다음과 같습니다.

- **USB 드라이브 탑재 및 언모트:** USB 드라이브가 탑재되거나 탑재되지 않은 경우 생성되는 감사 이벤트입니다.
- **PnP:** 플러그 앤 플레이 감사 이벤트는 이동식 저장소, 프린터 또는 미디어가 Bluetooth 생성됩니다.

## <a name="monitor-device-control-security"></a>장치 제어 보안 모니터링

끝점용 Microsoft Defender의 장치 제어를 통해 보안 관리자는 보고서를 통해 조직의 장치 제어 보안을 추적할 수 있는 도구를 사용할 수 있습니다. 보고서 및 장치 보호로 Microsoft 365 보안 센터에서 장치 제어 **보고서를 > 있습니다.**

보고서 대시보드의 장치  보호 카드에는 지난 180일 동안 미디어 유형에 의해 생성된 감사 이벤트 수가 표시됩니다.

> [!div class="mx-imgBorder"]
> ![DeviceControlReportCard](images/devicecontrolcard.png)

세부 **정보 보기 단추는** 장치 제어 보고서 페이지에 더 많은 미디어 사용 현황 **데이터를** 보여 줍니다.

이 페이지에서는 유형당 집계된 이벤트 수와 이벤트 목록을 제공하는 대시보드를 제공합니다. 관리자는 시간 범위, 미디어 클래스 이름 및 장치 ID를 필터링할 수 있습니다.

> [!div class="mx-imgBorder"]
> ![DeviceControlReportDetails](images/Detaileddevicecontrolreport.png)

이벤트를 선택하면 자세한 정보를 표시하는 플라이아웃이 나타납니다.

- **일반 세부 정보:** 날짜, 작업 모드 및 이 이벤트의 정책입니다.
- **미디어 정보:** 미디어 정보에는 미디어 이름, 클래스 이름, 클래스 GUID, 장치 ID, 공급업체 ID, 볼륨, 일련 번호 및 버스 유형이 포함됩니다.
- **위치 세부 정보:** 장치 이름 및 MDATP 장치 ID입니다.

> [!div class="mx-imgBorder"]
> ![FilterOnDeviceControlReport](images/devicecontrolreportfilter.png)

조직 전체에서 이 미디어에 대한 실시간 활동을 표시하려면 고급 헌팅 **열기 단추를** 선택합니다. 여기에는 미리 정의된 포함된 쿼리가 포함됩니다.

> [!div class="mx-imgBorder"]
> ![QueryOnDeviceControlReport](images/Devicecontrolreportquery.png)

장치의 보안을 확인하려면 플라이아웃에서 장치 **열기 페이지** 단추를 선택합니다. 이 단추를 클릭하면 장치 엔터티 페이지가 열립니다.

> [!div class="mx-imgBorder"]
> ![DeviceEntityPage](images/Devicesecuritypage.png)

## <a name="reporting-delays"></a>보고 지연

디바이스 제어 보고서는 미디어 연결이 발생하는 시간부터 이벤트가 카드 또는 도메인 목록에 반영되는 시간까지 12시간이 지연될 수 있습니다.