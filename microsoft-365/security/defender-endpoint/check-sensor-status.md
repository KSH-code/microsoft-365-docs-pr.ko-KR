---
title: 끝점용 Microsoft Defender에서 센서의 상태 확인
description: 장치의 센서 상태 확인을 통해 잘못 구성되거나, 비활성 상태인 경우 또는 센서 데이터를 보고하지 않는지 확인할 수 있습니다.
keywords: 센서, 센서 상태, 잘못 구성된, 비활성, 센서 데이터 없음, 센서 데이터, 통신 장애, 통신
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
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: e7794f99b21939c3cf51f4b5afe2b9da50f9b933
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60207070"
---
# <a name="check-sensor-health-state-in-microsoft-defender-for-endpoint"></a>끝점에 대한 Microsoft Defender의 센서 상태 확인

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-checksensor-abovefoldlink)

센서 **문제가 있는 디바이스 타일은** 보안 작업 대시보드에서 찾을 수 있습니다. 이 타일은 센서 데이터를 제공하고 Endpoint 서비스용 Defender와 통신하는 개별 디바이스의 능력에 대한 정보를 제공합니다. 주의가 필요한 장치 수를 보고하고 문제가 있는 장치를 식별하고 알려진 문제를 수정하기 위한 조치를 취하는 데 도움이 됩니다.

타일에는 서비스에 올바르게 보고하지 않는 장치 수에 대한 정보를 제공하는 두 가지 상태 표시기가 있습니다.

- **잘못 구성되었습니다.** 이러한 장치는 센서 데이터를 부분적으로 Endpoint용 Defender 서비스에 보고하고 수정해야 하는 구성 오류가 있을 수 있습니다.
- **비활성** - 지난 달에 7일 이상 Endpoint용 Defender 서비스에 보고를 중지한 장치.

그룹을 클릭하면 선택에 따라 필터링된 **장치** 목록으로 연결됩니다.

![센서 문제 타일이 있는 장치의 스크린샷.](images/atp-devices-with-sensor-issues-tile.png)

장치 **목록에서** 다음 상태를 사용하여 상태 목록을 필터링할 수 있습니다.

- **Active** - 끝점용 Defender 서비스에 적극적으로 보고하는 장치입니다.
- **잘못 구성되었습니다.** 이러한 장치는 센서 데이터를 부분적으로 Endpoint용 Defender 서비스에 보고하지만 수정해야 하는 구성 오류가 있을 수 있습니다. 잘못 구성된 장치에는 다음 문제 중 하나 또는 문제의 조합이 있을 수 있습니다.
  - **센서 데이터가 없음** - 장치가 센서 데이터 전송을 중지했습니다. 장치에서 제한된 경고를 트리거할 수 있습니다.
  - **통신 장애** - 장치와 통신하는 기능이 저하됩니다. 심층 분석을 위한 파일 전송, 파일 차단, 네트워크에서 장치 분리, 장치와 통신이 필요한 기타 작업이 작동하지 않을 수 있습니다.
- **비활성** - 끝점 서비스에 대한 Defender 보고를 중지한 장치.

내보내기 기능을 사용하여 전체 목록을 CSV 형식으로 다운로드할 **수도** 있습니다. 필터에 대한 자세한 내용은 장치 목록 [보기 및 구성을 참조하세요.](machines-view-overview.md)

> [!NOTE]
> CSV 형식으로 목록을 내보내 필터되지 않은 데이터를 표시합니다. CSV 파일에는 보기 자체에 적용된 필터링에 관계없이 조직의 모든 장치가 포함되고 조직의 규모에 따라 다운로드하는 데 많은 시간이 걸릴 수 있습니다.

![장치 목록 페이지의 스크린샷.](images/atp-devices-list-page.png)

잘못 구성되거나 비활성 장치를 클릭할 때 장치 세부 정보를 볼 수 있습니다.

## <a name="see-also"></a>참고 항목

- [Endpoint용 Defender에서 불안정한 센서 수정](fix-unhealthy-sensors.md)
- [클라이언트 분석기 개요](overview-client-analyzer.md)
- [클라이언트 분석기 다운로드 및 실행](download-client-analyzer.md)
- [Windows에서 클라이언트 분석기 실행](run-analyzer-windows.md)
- [macOS 또는 Linux에서 클라이언트 분석기 실행](run-analyzer-macos-linux.md)
- [Windows에서 고급 문제 해결을 위한 데이터 수집](data-collection-analyzer.md)
