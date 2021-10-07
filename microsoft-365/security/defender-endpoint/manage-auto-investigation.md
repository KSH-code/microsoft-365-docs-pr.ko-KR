---
title: 자동화된 조사 후 수정 작업 검토
description: 자동화된 조사 후 재구성 작업을 검토하고 승인(또는 거부)합니다.
keywords: autoir, 자동화, 조사, 감지, 수정, 작업, 보류 중, 승인됨
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: JoeDavies-MSFT
ms.author: josephd
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: how-to
ms.date: 01/29/2021
ms.technology: mde
ms.openlocfilehash: 22229d495e9b7694d07f25b60e854240f7c420c8
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60152037"
---
# <a name="review-remediation-actions-following-an-automated-investigation"></a>자동화된 조사 후 수정 작업 검토

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


## <a name="remediation-actions"></a>수정 작업

자동화된 [조사가](automated-investigations.md) 실행될 때 조사된 각 증거 조각에 대한 판결이 생성됩니다. 판정은 *악성,* *의심스러운* 또는 *위협이 없음일 수 있습니다.*

에 따라 다를 수 있습니다.

- 위협 유형,
- 결과 결과 및
- 조직의 장치 [그룹](/microsoft-365/security/defender-endpoint/machine-groups) 구성 방법

수정 작업은 자동으로 또는 조직의 보안 운영 팀의 승인 시에만 발생할 수 있습니다.

다음은 몇 가지 예입니다.

- **예제 1:** Fabrikam의 장치 그룹이 **전체 -** 위협을 자동으로 수정합니다(권장 설정). 이 경우 자동화된 조사 후 악의적인 것으로 간주되는 아티팩트에 대해 수정 작업이 자동으로 [수행됩니다(완료된](#review-completed-actions)작업 검토 참조).

- **예제 2:** Contoso의 장치는 Semi - 모든 수정에 대한 승인이 필요한 장치 그룹에 **포함되어 있습니다.** 이 경우 Contoso의 보안 운영 팀은 자동화된 조사 후 모든 수정 작업을 검토하고 승인해야 [합니다(보류 중인](#review-pending-actions)작업 검토 참조).

- **예제 3:** Tailspin Toys의 장치 그룹이 **자동화된** 응답 없음(권장하지 않음)으로 설정되어 있습니다. 이 경우 자동화된 조사가 발생하지 않습니다. 수정 작업이 수행되거나 보류 중이 아니며, 장치에 [](/microsoft-365/security/defender-endpoint/auto-investigation-action-center#the-action-center) 대한 관리 센터에 작업이 [기록되지 않습니다(장치](/microsoft-365/security/defender-endpoint/machine-groups#manage-device-groups)그룹 관리 참조).

자동 또는 승인 시 자동화된 조사를 수행하면 하나 이상의 수정 작업이 수행될 수 있습니다.

- 파일 Quarantine a file
- 레지스트리 키 제거
- 프로세스 숨기기
- 서비스 중지
- 드라이버를 사용하지 않도록 설정
- 예약된 작업 제거

## <a name="review-pending-actions"></a>보류 중인 작업 검토

1. 보안 Microsoft 365()로 이동하여 [https://security.microsoft.com](https://security.microsoft.com) 로그인합니다.
2. 탐색 창에서 **작업 센터** 를 선택합니다.
3. 보류 중인 **탭의 항목을 검토합니다.**
4. 플라이아웃 창을 여는 작업을 선택합니다.
5. 플라이아웃 창에서 정보를 검토한 후 다음 단계 중 하나를 수행합니다.
   - 조사에 대한 자세한 내용을 **확인하려면** 조사 페이지 열기 를 선택합니다.
   - **승인을** 선택하여 보류 중인 작업을 초기화합니다.
   - 보류 **중인** 작업이 수행되지 않도록 방지하려면 거부를 선택합니다.
   - 이동을 **선택하여** 고급 헌팅으로 [이동합니다.](advanced-hunting-overview.md)

## <a name="review-completed-actions"></a>완료된 작업 검토

1. 보안 Microsoft 365()로 이동하여 [https://security.microsoft.com](https://security.microsoft.com) 로그인합니다.
2. 탐색 창에서 **작업 센터** 를 선택합니다.
3. 기록 탭의 **항목을 검토합니다.**
4. 해당 수정 조치에 대한 자세한 내용을 확인하려면 항목을 선택합니다.

## <a name="undo-completed-actions"></a>완료된 작업 취소

장치 또는 파일이 위협이 아닌 것으로 확인되면 해당 작업이 자동으로 또는 수동으로 수행된 경우 수행된 수정 작업을 실행 취소할 수 있습니다. 작업 센터의 사용 기록 **탭에서** 다음 작업을 실행 취소할 수 있습니다.

<br>

****

|작업 원본|지원되는 작업|
|---|---|
|<ul><li>자동화된 조사</li><li>Microsoft Defender 바이러스 백신</li><li>수동 응답 작업</li></ul>|<ul><li>디바이스 격리</li><li>코드 실행 제한</li><li>파일 Quarantine a file</li><li>레지스트리 키 제거</li><li>서비스 중지</li><li>드라이버를 사용하지 않도록 설정</li><li>예약된 작업 제거</li></ul>|
|

### <a name="to-undo-multiple-actions-at-one-time"></a>한 번씩 여러 작업을 취소하는 경우

1. Go to the Action center ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) and sign in.
2. 사용 **기록 탭에서** 취소할 작업을 선택합니다. 동일한 작업 유형이 있는 항목을 선택해야 합니다. 플라이아웃 창이 열립니다.
3. 플라이아웃 창에서 **취소를 선택합니다.**

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a>여러 장치에서 파일을 검지에서 제거하려면

1. Go to the Action center ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) and sign in.
2. 사용 **기록 탭에서** 작업 유형이 **Quarantine** 파일이 인 항목을 선택합니다.
3. 플라이아웃 창에서 이 파일의 X 추가 인스턴스에 **적용을 선택한** 다음 실행 **취소를 선택합니다.**

## <a name="automation-levels-automated-investigation-results-and-resulting-actions"></a>자동화 수준, 자동화된 조사 결과 및 결과 작업

자동화 수준은 특정 수정 작업이 자동으로 수행될지 승인 시에만 수행될지 여부에 영향을 미치게 됩니다. 경우에 따라 보안 운영 팀에서 자동화된 조사 결과에 따라 추가 조치를 취할 수 있습니다. 다음 표에는 자동화 수준, 자동화된 조사 결과 및 각 사례에서 어떤 작업을 할지 요약되어 있습니다.

<br>

****

|장치 그룹 설정|자동화된 조사 결과|수행할 작업|
|---|---|---|
|**전체 - 위협을 자동으로** 수정(권장 설정)|악의적인 *판정은* 증거에 도달합니다. <p> 적절한 수정 작업이 자동으로 수행됩니다.|[완료된 작업 검토](#review-completed-actions)|
|**전체 - 자동으로 위협 수정**|증거에 *대한 의심스러운* 판정에 도달합니다. <p> 재구성 작업은 계속하기 위해 승인을 보류 중입니다.|[보류 중인 작업 승인(또는 거부)](#review-pending-actions)|
|**Semi - 모든 수정에 대한 승인 필요**|증거를 위해 악성  또는 *의심스러운* 판정에 도달합니다. <p> 재구성 작업은 계속하기 위해 승인을 보류 중입니다.|[보류 중인 작업 승인(또는 거부)](#review-pending-actions)|
|**Semi - 핵심 폴더 수정에 대한 승인 필요**|악의적인 *판정은* 증거에 도달합니다. <p> 아티팩트가 파일 또는 실행 파일인 경우 Windows 파일 폴더와 같은 운영 체제 디렉터리에 있는 경우 수정 작업이 승인 보류 중입니다. <p> 아티팩트가 운영 체제 *디렉터리에* 없는 경우 수정 작업이 자동으로 수행됩니다.|<ol><li>[보류 중인 작업 승인(또는 거부)](#review-pending-actions)</li><li>[완료된 작업 검토](#review-completed-actions)</li></ol>|
|**Semi - 핵심 폴더 수정에 대한 승인 필요**|증거에 *대한 의심스러운* 판정에 도달합니다. <p> 수정 작업이 승인 보류 중입니다.|[보류 중인 작업을 승인(또는 거부) 합니다.](#review-pending-actions)|
|**Semi - 비 임시 폴더 수정에 대한 승인 필요**|악의적인 *판정은* 증거에 도달합니다. <p> 아티팩트가 사용자의 다운로드 폴더 또는 임시 폴더와 같이 임시 폴더에 없는 파일 또는 실행 파일인 경우 수정 작업은 승인 보류 중입니다. <p> 아티팩트가 임시 폴더에  있는 파일 또는 실행 파일인 경우 수정 작업이 자동으로 수행됩니다.|<ol><li>[보류 중인 작업 승인(또는 거부)](#review-pending-actions)</li><li>[완료된 작업 검토](#review-completed-actions)</li></ol>|
|**Semi - 비 임시 폴더 수정에 대한 승인 필요**|증거에 *대한 의심스러운* 판정에 도달합니다. <p> 수정 작업이 승인 보류 중입니다.|[보류 중인 작업 승인(또는 거부)](#review-pending-actions)|
|모든 **전체** 또는 **세미** 자동화 수준|증거에 *대한* 위협 없음에 대한 판결이 도달했습니다. <p> 재구성 작업은 수행하지 않습니다. 승인 보류 중인 작업은 없습니다.|[자동화된 조사의 세부 정보 및 결과 보기](/microsoft-365/security/defender-endpoint/auto-investigation-action-center)|
|**자동 응답** 없음(권장하지 않음)|자동화된 조사가 실행되지 않습니다. 따라서 판정에 도달하지 못하고 수정 작업이 수행되거나 승인을 기다리지 않습니다.|[전체 또는 세미 자동화를  사용할 수 있도록 장치 그룹을 **설정하거나 변경하는 것을 고려합니다.**](/microsoft-365/security/defender-endpoint/machine-groups)|
|

끝점용 Microsoft Defender에서 모든 판정은 관리 [센터에서 추적됩니다.](auto-investigation-action-center.md#new-a-unified-action-center)

## <a name="next-steps"></a>다음 단계

- [라이브 응답 기능에 대해 자세히 알아보시겠습니다.](live-response.md)
- [고급 헌팅을 통해 위협을 사전 대응](advanced-hunting-overview.md)
- [Endpoint용 Microsoft Defender에서 가양성/가음성 처리](defender-endpoint-false-positives-negatives.md)

## <a name="see-also"></a>참고 항목

- [자동 조사 개요](automated-investigations.md)
