---
title: 디바이스용 Microsoft Secure Score
description: 장치에 대한 점수는 응용 프로그램, 운영 체제, 네트워크, 계정 및 보안 제어 전반에 걸쳐 디바이스의 총 보안 구성 상태를 보여줍니다.
keywords: Microsoft Secure Score for Devices, Endpoint Microsoft Defender for Devices, Secure score, configuration score, 위협 및 취약성 관리, security controls, improvement opportunities, security configuration score over time, security posture, baseline
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: ec39f07ff653b3c28c645978c0a708da37d348dc
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60206760"
---
# <a name="microsoft-secure-score-for-devices"></a>디바이스용 Microsoft Secure Score

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**

- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [위협 및 취약성 관리](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)

> [!NOTE]
> 구성 점수는 이제 장치용 Microsoft 위협 및 취약성 관리 점수의 일부입니다.

디바이스에 대한 점수는 위협 및 취약성 관리 포털의 [Microsoft 365 Defender](tvm-dashboard-insights.md) 표시됩니다. 장치에 대한 Microsoft 보안 점수가 높을수록 끝점이 사이버 보안 위협 공격으로부터 더 탄력적입니다. 다음 범주에 걸쳐 디바이스의 전체 보안 구성 상태를 반영합니다.

- 응용 프로그램
- 운영 체제
- 네트워크
- 계정
- 보안 제어

보안 권장 사항 페이지로 이동하여 관련 권장 사항을 볼 범주를 선택합니다. [](tvm-security-recommendation.md)

## <a name="turn-on-the-microsoft-secure-score-connector"></a>Microsoft 보안 점수 커넥터 켜기

끝점 신호를 위해 Microsoft Defender를 전달하여 장치 보안 상태의 Microsoft 보안 점수를 볼 수 있도록 합니다. 전달된 데이터는 Microsoft 보안 점수 데이터와 동일한 위치에 저장되고 처리됩니다.

변경 내용을 대시보드에 반영하는 데 최대 몇 시간이 걸릴 수 있습니다.

1. 탐색 창에서 끝점 **설정** \>  \> **고급** 기능으로 \> **이동**

2. **아래로 스크롤하여 Microsoft 보안** 점수로 이동하고 설정을 으로 **전환합니다.**

3. 기본 **설정 저장을 선택합니다.**

## <a name="how-it-works"></a>작업 방법

> [!NOTE]
> Microsoft Secure Score for Devices는 현재 그룹 정책을 통해 설정된 구성을 지원합니다. 현재 부분 Intune 지원으로 인해 Intune을 통해 설정될 수 있는 구성이 잘못 구성된 것으로 표시될 수 있습니다. 조직에서 보안 구성 관리를 위해 Intune을 사용하는 경우 IT 관리자에게 문의하여 실제 구성 상태를 확인할 수 있습니다.

Microsoft Secure Score for Devices 카드의 데이터는 세세하고 지속적인 취약점 검색 프로세스의 제품입니다. 다음을 지속적으로 구성 검색 평가를 통해 집계됩니다.

- 수집된 구성을 수집된 벤치마크와 비교하여 잘못 구성된 자산 검색
- 수정 또는 부분적으로 수정될 수 있는 취약성에 구성 매핑(위험 감소)
- 모범 사례 구성 벤치마크 수집 및 유지 관리(공급업체, 보안 피드, 내부 연구 팀)
- 모든 자산에서 보안 제어 구성 상태의 변경 사항 수집 및 모니터링

## <a name="improve-your-security-configuration"></a>보안 구성 개선

보안 권장 사항 목록의 문제를 수정하여 보안 구성을 개선합니다. 이렇게 할 때 장치에 대한 Microsoft 보안 점수가 개선될 수 있으며 조직은 사이버 보안 위협 및 취약성에 대해 더 탄력적으로 대응할 수 있습니다.

1. 위협 및 취약성 관리 대시보드의 Microsoft 장치 보안 점수 카드에서 범주 중 하나를 선택합니다. 해당 범주와 관련된 추천 목록을 볼 수 있습니다. 보안 권장 사항 [**페이지로 이동합니다.**](tvm-security-recommendation.md) 모든 보안 권장 사항을 확인하려는 경우 보안 권장 사항 페이지로 이동한 후 검색 필드를 지우십시오.

2. 목록에서 항목을 선택합니다. 추천과 관련된 세부 정보가 있는 플라이아웃 패널이 열립니다. 수정 **옵션 을 선택합니다.**

   :::image type="content" alt-text="보안은 관련 보안 권장 사항을 제어합니다." source="images/security-controls.png":::

3. 설명을 읽어 문제의 컨텍스트와 다음에 할 작업을 이해합니다. 기한을 선택하고 메모를 추가하고, 추가 작업 수행을 위해 전자 메일에 첨부할 수 있도록 모든 재구성 활동 데이터를 **CSV로** 내보내기 를 선택합니다.

4. **요청을 제출합니다.** 재구성 작업이 만들어졌다는 확인 메시지가 표시됩니다.

   :::image type="content" alt-text="재구성 작업 만들기 확인." source="images/remediation-task-created.png":::

5. CSV 파일을 저장합니다.

   :::image type="content" alt-text="csv 파일을 저장합니다." source="images/tvm_save_csv_file.png":::

6. IT 관리자에게 후속 전자 메일을 보내고 수정을 위해 시스템에서 전파하도록 허용하는 시간을 허용합니다.

7. 대시보드에서 **Microsoft Secure Score for Devices(장치용 Microsoft 보안 점수)** 카드를 다시 검토합니다. 권장 보안 제어의 수가 감소합니다. 보안 **컨트롤을** 선택하여 보안 권장  사항 페이지로 돌아가면 해결한 항목이 더 이상 목록에 나열되지 않습니다. 장치에 대한 Microsoft 보안 점수가 높아야 합니다.

> [!IMPORTANT]
>취약성 평가 감지 비율을 높이기 위해 다음과 같은 필수 보안 업데이트를 다운로드하여 네트워크에 배포합니다.
>
> - 19H1 고객 | [KB 4512941](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)
> - RS5 고객 | [KB 4516077](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)
> - RS4 고객 | [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)
> - RS3 고객 | [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)
>
> 보안 업데이트를 다운로드하려면
>
> 1. Microsoft [업데이트 카탈로그로 이동하십시오.](https://www.catalog.update.microsoft.com/home.aspx)
> 2. 다운로드해야 하는 보안 업데이트 KB 번호에 키를 입력한 다음 검색을 **클릭합니다.**

## <a name="related-topics"></a>관련 항목

- [위협 및 취약성 관리 개요](next-gen-threat-and-vuln-mgt.md)
- [대시보드](tvm-dashboard-insights.md)
- [노출 점수](tvm-exposure-score.md)
- [보안 권장 사항](tvm-security-recommendation.md)
