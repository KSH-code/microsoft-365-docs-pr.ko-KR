---
title: 클라이언트 분석기 HTML 보고서 이해
description: Endpoint 클라이언트 분석기 HTML 보고서용 Microsoft Defender를 분석하는 방법 학습
keywords: 클라이언트 분석기 보고서, html 보고서, 클라이언트 분석기
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 735b2a0331e399fa7bf3444ff8e5326898c038b4
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59187587"
---
# <a name="understand-the-client-analyzer-html-report"></a>클라이언트 분석기 HTML 보고서 이해

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2146631)

클라이언트 분석기는 HTML 형식으로 보고서를 생성합니다. 문제를 해결할 수 있도록 보고서를 검토하여 잠재적인 센서 문제를 식별하는 방법을 배워야 합니다.

다음 예제를 사용하여 보고서를 이해합니다.

 컴퓨터 온보딩된 분석기에서 만료된 Org ID로 출력하고 끝점 URL에 필요한 Microsoft Defender URL 중 하나에 도달하지 못하는 예제:

![클라이언트 분석기 결과의 이미지입니다.](images/147cbcf0f7b6f0ff65d200bf3e4674cb.png)

- 맨 위에 참조를 위해 스크립트 버전 및 스크립트 런타임이 나열됩니다.
- 장치 **정보 섹션에서는** 분석기가 실행된 장치를 고유하게 식별하는 기본 OS 및 장치 식별자를 제공합니다.
- **Endpoint 보안 세부 정보는** 끝점 및 센서 프로세스를 포함하여 끝점 관련 프로세스에 대한 Microsoft Defender에 Microsoft Defender 바이러스 백신 정보를 제공합니다. 중요한 프로세스가 온라인이 아닌 경우 색이 빨강으로 변경됩니다.

  ![클라이언트 분석기 자세한 결과의 이미지](images/85f56004dc6bd1679c3d2c063e36cb80.png)

-   **Endpoint 보안 세부 정보는** 끝점 및 센서 프로세스를 포함하여 끝점 관련 프로세스에 대한 Microsoft Defender에 Microsoft Defender 바이러스 백신 정보를 제공합니다. 중요한 프로세스가 온라인이 아닌 경우 색이 빨강으로 변경됩니다.

![클라이언트 분석기 세부 결과의 이미지입니다.](images/85f56004dc6bd1679c3d2c063e36cb80.png)

-   결과 **확인 요약에서** 분석기에서 검색된 오류, 경고 또는 정보 이벤트에 대한 집계된 수를 하게 됩니다.

-   자세한 **결과에는** 결과가 있는 목록(심각도별로 정렬)과 분석기에서 관찰한 결과를 기반으로 하는 지침이 표시됩니다.

## <a name="open-a-support-ticket-to-microsoft-and-include-the-analyzer-results"></a>Microsoft에 대한 지원 티켓을 열고 분석기 결과 포함

지원 티켓을 열 때 분석기 결과 파일을 [포함하려면](contact-support.md#open-a-service-request)첨부 파일 섹션을 사용하여 파일을 포함해야  `MDEClientAnalyzerResult.zip` 합니다.

![첨부 파일 프롬프트 이미지입니다.](images/508c189656c3deb3b239daf811e33741.png)

> [!NOTE]
> 파일 크기가 25MB보다 큰 경우 사례에 할당된 기술 지원 엔지니어가 분석을 위해 대용량 파일을 업로드하는 전용 보안 작업 영역이 제공될 것입니다.
