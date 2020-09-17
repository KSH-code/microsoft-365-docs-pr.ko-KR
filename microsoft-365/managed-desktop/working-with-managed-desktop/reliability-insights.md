---
title: 안정성 인사이트
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 06e1446ca290439c9e6689f4461c825438cf6aaf
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950345"
---
# <a name="reliability-insights"></a>안정성 인사이트

이 보기는 관리 되는 장치에 대 한 상태 요약을 제공 합니다. 안정성 데이터를 보려면 **안정성** 탭을 선택 합니다.


![안정성 창: 왼쪽 위에 있는 장치 간의 안정성, 오른쪽 위의 안정성 그래프, 아래쪽에 있는 상위 문제 테이블 오른쪽 아래에 도움말 및 피드백 단추가 있습니다.](../../media/insights_reliability.png)

**Devices에서의 안정성** 섹션에서는 "정상"으로 간주 되는 장치의 비율과 마지막으로 보고 된 오류 이후 관찰 된 평균 시간을 보고 하 여 지난 14 일 동안의 배포에 대 한 신속한 상태 요약을 제공 합니다. 

 
오른쪽의 **안정성** 그래프에는 치명적인 오류가 발생 한 장치 수와 시간이 경과 함에 따라 관찰 된 중대 한 오류 총 수가 표시 됩니다.

**주요 문제** 섹션에는 관리 되는 장치 중 5% 이상에 영향을 주는 특정 검색 된 문제에 대 한 세부 정보가 나와 있습니다. 보고 된 세부 정보는 다음과 같습니다.

- 문제 유형
    - 앱 작동이 중지 되거나 예기치 않게 중지 되는 응용 프로그램 중단
    - 응용 프로그램이 중단 되며, 응용 프로그램에서 입력에 대 한 응답을 중지 함
    - 치명적인 오류-Windows에 문제가 발생 하 여 복구할 수 없는 경우 발생 합니다.
- 같은 문제로 인해 영향을 받는 장치 수입니다.
- 해당 숫자가 나타내는 관리 되는 장치의 백분율
- 특정 문제가 발생 한 총 횟수입니다.
- 문제의 원인이 되는 것으로 표시 되는 소프트웨어 구성 요소입니다.
- 검색 된 문제의 범주:
    - 브라우저 (Edge, Chrome, IE)
    - 알 수 없음 (Microsoft 구성 요소 아님)
    - 드라이버 (오디오, 그래픽 또는 기타 드라이버)
    - 생산성 (여유 시간, G-제품군, Microsoft Office 및 해당 추가 기능 또는 확장, 팀)
    - 미디어 (이미지, 음악 또는 비디오 앱)
    - 보안 (Windows 보안 구성 요소)
- Microsoft Managed Desktop 작업으로 인 한 현재 상태 조사 및 remediates 문제 해결

