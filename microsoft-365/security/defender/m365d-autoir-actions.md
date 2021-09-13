---
title: 관리 센터에서 작업 보기 및 관리
description: 관리 센터를 사용하여 수정 작업 보기 및 관리
keywords: 조치, 센터, 자동 공기, 자동화, 조사, 대응, 수정
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: daedba79bb2fd9ac452cbef08d74d4d876122478
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59213295"
---
# <a name="view-and-manage-actions-in-the-action-center"></a>관리 센터에서 작업 보기 및 관리

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

위협 방지 기능의 Microsoft 365 Defender 수정 작업이 수행될 수 있습니다. 다음은 몇 가지 예입니다.

- [자동화된 조사를](m365d-autoir.md) 수행하면 수정 작업이 자동으로 수행되거나 승인을 기다립니다.
- 바이러스 백신, 맬웨어 방지 및 기타 위협 방지 기능은 파일, URL 또는 프로세스를 차단하거나 아티팩트를 검역에 보내는 등의 수정 작업을 수행할 수 있습니다.
- 보안 운영 팀은 고급 헌팅 중이나 경고 [](advanced-hunting-overview.md) 또는 인시던트 [](investigate-alerts.md) 조사 중과 같은 수동으로 수정 작업을 수행할 [수 있습니다.](investigate-incidents.md)

> [!NOTE]
> 수정 작업을 승인하거나 거부하려면 [적절한 사용 권한](m365d-action-center.md#required-permissions-for-action-center-tasks)이 있어야 합니다. 자세한 내용은 선행 [준비를 참조하세요.](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)

## <a name="review-pending-actions-in-the-action-center"></a>작업 센터에서 보류 중인 작업 검토

자동화된 조사가 진행되고 적시에 완료될 수 있도록 가능한 한 빨리 보류 중인 작업을 승인하거나 거부하는 것이 중요합니다. 

1. [https://security.microsoft.com](https://security.microsoft.com)으로 이동하여 로그인합니다. 

2. 탐색 창에서 **작업 센터** 를 선택합니다. 

3. 작업 센터의 보류 중인 **탭에서** 목록의 항목을 선택합니다. 플라이아웃 창이 열립니다. 다음은 예입니다.

   ![작업을 승인하거나 거부합니다.](../../media/air-actioncenter-itemselected.png)

4. 플라이아웃 창의 정보를 검토한 후 다음 단계 중 하나를 수행합니다.
   - 조사에 대한 자세한 내용을 **확인하려면** 조사 페이지 열기 를 선택합니다.
   - **승인을** 선택하여 보류 중인 작업을 초기화합니다.
   - 보류 **중인** 작업이 수행되지 않도록 방지하려면 거부를 선택합니다.
   - 이동을 **선택하여** 고급 헌팅으로 [이동합니다.](advanced-hunting-overview.md) 

## <a name="undo-completed-actions"></a>완료된 작업 취소

장치 또는 파일이 위협이 아닌 것으로 확인되면 해당 작업이 자동으로 또는 수동으로 수행된 경우 수행된 수정 작업을 실행 취소할 수 있습니다. 작업 센터의 사용 기록 **탭에서** 다음 작업을 실행 취소할 수 있습니다.  

| 작업 원본 | 지원되는 작업 |
|:---|:---|
| - 자동화된 조사 <br/>- Microsoft Defender 바이러스 백신 <br/>- 수동 응답 작업 | - 장치 격리 <br/>- 코드 실행 제한 <br/>- 파일 Quarantine a file <br/>- 레지스트리 키 제거 <br/>- 서비스 중지 <br/>- 드라이버를 사용하지 않도록 설정 <br/>- 예약된 작업 제거 |

### <a name="undo-one-remediation-action"></a>한 가지 수정 작업 실행 취소

1. Go to the Action center ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) and sign in.

2. 사용 **기록 탭에서** 실행 취소할 작업을 선택합니다.

3. 화면 오른쪽 창에서 **취소를 선택합니다.**

### <a name="undo-multiple-remediation-actions"></a>여러 수정 작업 취소

1. Go to the Action Center ( https://security.microsoft.com/action-center) and sign in.

2. 사용 **기록 탭에서** 취소할 작업을 선택합니다. 동일한 작업 유형이 있는 항목을 선택해야 합니다. 플라이아웃 창이 열립니다.

3. 플라이아웃 창에서 **취소를 선택합니다.**

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a>여러 장치에서 파일을 검지에서 제거하려면 

1. Go to the Action center ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) and sign in.

2. 기록 **탭에서** 파일 **Quarantine file** Action 형식이 있는 파일을 선택합니다.

3. 화면 오른쪽 창에서 이 파일의 X **추가** 인스턴스에 적용을 선택한 다음 실행 **취소를 선택합니다.**

## <a name="next-steps"></a>다음 단계

- [자동화 조사 세부정보 및 결과 보기](m365d-autoir-results.md)
- [가짓 긍정 또는 거짓 부정 해결](m365d-autoir-report-false-positives-negatives.md)
