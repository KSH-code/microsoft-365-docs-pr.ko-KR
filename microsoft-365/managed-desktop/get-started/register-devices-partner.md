---
title: 파트너에 대 한 Microsoft Managed Desktop의 장치 등록
description: 파트너가 장치를 등록 하 여 Microsoft managed Desktop에서 관리할 수 있도록 하는 방법
ms.prod: w10
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: d743092fdd309c1afd748afa7523f0cc0c6a2fd0
ms.sourcegitcommit: cf77e4bf69e6ae144563f1e764ea3437ed6fc836
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/25/2019
ms.locfileid: "33295884"
---
# <a name="register-devices-in-microsoft-managed-desktop-for-partners"></a>파트너에 대 한 Microsoft Managed Desktop의 장치 등록


이 항목에서는 파트너가 장치를 등록 하기 위해 수행 해야 하는 단계에 대해 설명 합니다. 장치를 직접 등록 하는 프로세스는 [Microsoft Managed Desktop의 등록 장치에 직접](register-devices-self.md)기록 됩니다.



## <a name="prepare-for-registration"></a>등록 준비 
고객에 대 한 등록을 완료 하기 전에 먼저 [파트너 센터](https://partner.microsoft.com/dashboard)에서 해당 사용자와의 관계를 설정 해야 합니다. 자세한 내용은 [파트너 센터 도움말을 참조](https://docs.microsoft.com/en-us/partner-center/request-a-relationship-with-a-customer)하십시오.

고객에 대 한 등록을 완료 하려면 먼저 CSV 파일을 만듭니다.

>[!NOTE]
>편의상이 *파트너 버전* 의 CSV 파일에 대 한 [서식 파일](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.xlsx) 을 다운로드할 수 있습니다.

샘플 1과 **정확히 같은 열 머리글** 을 포함 해야 하지만 (제조업체, 모델 등), 다른 행에 대 한 고유한 데이터를 포함할 수 있습니다. 서식 파일을 사용 하는 경우 메모장 등의 텍스트 편집 도구에서이 템플릿을 열고 행 2와 아래에 데이터만 입력 하는 것이 좋습니다. 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,
  
  
  ```


>[!NOTE]
>이 형식은 파트너 프로세스에만 해당 됩니다. 자동 등록 프로세스는 [Microsoft Managed Desktop의 등록 장치에서 직접](register-devices-self.md)설명 됩니다.

>[!IMPORTANT]
>이러한 값은 SMBIOS의 제조업체 값과 정확 하 게 일치 해야 합니다. 첫 번째 행에는 *하드웨어 해시* (두 번째 행의 값은 제외)도 포함 해야 하며 두 번째 행의 *일련 번호* 값 뒤에는 후행 쉼표가 있어야 합니다.

- 장치 제조업체 (예: SpiralOrbit) 
- 장치 모델 (예: ContosoABC)
- 장치 일련 번호

## <a name="register-devices-by-using-the-azure-portal"></a>Azure Portal을 사용 하 여 장치 등록

Azure portal을 사용 하 여 등록 하는 것은 다른 방법으로 포털에 액세스 하는 것을 제외 하 고 셀프 서비스와 동일 합니다. 다음 단계를 따릅니다.

1. [파트너 센터로](https://partner.microsoft.com/dashboard) 이동
2. **고객**을 선택 합니다.
3. 관리할 고객을 선택 합니다.
4. **서비스 관리**를 선택 합니다.
5. **Intune**을 선택 합니다.
6. Azure portal의 위쪽 검색 상자에서 "mmd"를 검색 합니다.
7. **장치**를 선택 합니다.
8. **파일 업로드**에서 이전에 만든 CSV 파일의 경로를 제공 합니다.
9. 원하는 경우 사용자의 추적 목적으로 **주문 id** 또는 **구매 ID** 를 추가할 수 있습니다. 이러한 값에 대 한 형식 요구 사항은 없습니다.
10. **장치 등록**을 선택 합니다. 시스템은 장치를 디바이스 **블레이드에서**장치 목록에 추가 하 고 **등록 보류 중**으로 표시 합니다. 등록은 일반적으로 10 분 미만이 걸리고, 성공적인 장치는 **사용자가** 사용할 준비가 된 것으로 표시 되 고 최종 사용자가 사용을 시작할 때까지 기다릴 수 있습니다.


기본 **Microsoft Managed Desktop-Devices** 페이지에서 장치 등록의 진행 상태를 모니터링할 수 있습니다. 다음과 같은 가능한 상태가 보고 됩니다.

| 시/도 | 설명 |
|---------------|-------------|
| 등록 보류 중 | 등록이 아직 완료 되지 않았습니다. 나중에 다시 확인 합니다. |
| 등록 실패 | 등록을 완료할 수 없습니다. 자세한 내용은 [문제 해결](register-devices-self.md#troubleshooting) 을 참조 하세요. |
| 사용자 준비 | 등록을 완료 했으며 이제 장치를 최종 사용자에 게 배달할 준비가 되었습니다. Microsoft Managed Desktop은 처음 설정할 때 가이드를 제공 하므로 추가 준비를 수행할 필요가 없습니다. |
| 활성 | 장치가 최종 사용자에 게 배달 되었으며 테 넌 트에 등록 되어 있습니다. 또한 장치를 정기적으로 사용 하는 것을 나타냅니다. |
| 있었던 | 장치가 최종 사용자에 게 배달 되었으며 테 넌 트에 등록 되어 있습니다. 그러나 최근에 최근 7 일 이내에 장치를 사용 하지 않았습니다.  |

## <a name="register-devices-by-using-an-api"></a>API를 사용 하 여 장치 등록

API로 등록 하는 기능은 셀프 서비스와 동일 하지만, CSV 섹션에 설명 된 것 처럼 장치 컬렉션의 하드웨어 해시 속성은 선택 사항 이라는 차이가 있습니다. 

## <a name="troubleshooting"></a>문제 해결

| 오류 메시지 | 세부 정보 |
|---------------|-------------|
| 장치를 찾을 수 없음 | 제공 된 제조업체, 모델 또는 일련 번호에 대해 일치 하는 항목을 찾을 수 없기 때문에이 장치를 등록할 수 없습니다. 장치 공급자에서 이러한 값을 확인 합니다. |
| 장치를 찾을 수 없음 | 이 디바이스가 조직에 없으므로 등록을 취소할 수 없습니다. 추가 작업이 필요 하지 않습니다. |
| 하드웨어 해시가 잘못 되었습니다. | 이 장치에 대해 제공한 하드웨어 해시가 올바르게 포맷 되지 않았습니다. 하드웨어 해시를 두 번 확인 한 다음 다시 제출 합니다. |
| 장치가 이미 등록 됨 | 이 장치는 이미 조직에 등록 되어 있습니다. 추가 작업이 필요 하지 않습니다. |
| 다른 조직에서 요구 하는 장치 | 이 장치는 다른 조직에서 이미 요구 되었습니다. 장치 공급자에 게 문의 하세요. |
| 예기치 않은 오류 | 요청을 자동으로 처리할 수 없습니다. 지원 서비스에<support link>문의 () 하 고 요청 ID를 제공 합니다.<requestId> |