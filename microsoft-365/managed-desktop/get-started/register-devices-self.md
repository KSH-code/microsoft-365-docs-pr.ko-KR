---
title: Microsoft Managed Desktop에서 직접 장치 등록
description: Microsoft managed Desktop에서 관리할 수 있도록 장치를 직접 등록
ms.prod: w10
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 02b3b7ab32ff92304ab27ca8e8c805ade803c971
ms.sourcegitcommit: cf77e4bf69e6ae144563f1e764ea3437ed6fc836
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/25/2019
ms.locfileid: "33296168"
---
# <a name="register-devices-in-microsoft-managed-desktop"></a>Microsoft Managed Desktop에서 장치 등록

>[!NOTE]
>이 항목에서는 직접 장치를 등록 하는 단계를 설명 합니다. 파트너에 대 한 프로세스는 [Microsoft Managed Desktop for partner의 등록 장치](register-devices-partner.md)에 설명 되어 있습니다.

Microsoft Managed Desktop은 새로운 장치에서 작동 하거나 이미 사용 중인 장치를 다시 사용할 수 있습니다 (다시 이미지 해야 함). Azure Portal에서 Microsoft Managed Desktop을 사용 하 여 장치를 등록 하거나 API를 사용 하 여 유연성을 확보할 수 있습니다.

## <a name="prepare-to-register-devices"></a>장치 등록 준비

사용할 장치를 아직 가져오지 않은 경우에는 [Microsoft Managed Desktop devices](../service-description/device-list.md) 를 확인 하 고 장치 파트너와 협력 하 여 지원 되는 장치를 조달 하세요.

완전히 새로운 장치에 대 한 작업을 수행 하 고 있거나 기존 항목을 다시 사용 하 여 Microsoft Managed Desktop에 등록 하 든, **CSV (쉼표로 구분 된) 파일**을 준비 해야 합니다. 이 파일에는 각 장치에 대 한 다음 정보가 포함 되어야 합니다.

>[!NOTE]
>이 형식은 셀프 서비스 등록 전용입니다. 파트너가 사용 해야 하는 형식 파트너는 [Microsoft Managed Desktop for partner의 등록 장치](register-devices-partner.md)에 문서화 되어 있어야 합니다.

이러한 값은 표시 목적으로 사용 되며 장치에서 속성을 정확히 일치 시 키 지 않아도 됩니다.
- 장치 제조업체 (예: SpiralOrbit) 
- 장치 모델 (예: ContosoABC)
- 장치 일련 번호

하드웨어 해시는 정확히 일치 해야 합니다.
- 하드웨어 해시

하드웨어 해시를 얻으려면 OEM 또는 파트너 로부터 도움을 요청 하거나 각 장치에 대해 다음 단계를 수행 합니다.

1.  관리 권한으로 PowerShell 프롬프트를 엽니다.
2.  실행`Install-Script -Name Get-WindowsAutoPilotInfo`
3.  실행`powershell -ExecutionPolicy Unrestricted Get-WindowsAutopilotInfo -OutputFile <path>\hardwarehash.csv`


또는 처음으로 OOBE를 진행 하기 전에 새 장치에서 다음 단계를 수행할 수 있습니다.

1. 다른 장치에서 USB 드라이브를 삽입 합니다.
2. 관리 권한으로 PowerShell 프롬프트를 엽니다.
3. 실행`Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`
4. 대상 장치를 켜고 설정 환경을 시작 하지 않습니다. 실수로 설치 환경을 시작한 경우 장치를 초기화 하거나 다시 이미지로 만들어야 합니다.
5. USB 드라이브를 삽입 한 다음 SHIFT + F10 키를 누릅니다.
6. 관리 권한으로 PowerShell 프롬프트를 열고를 실행 `cd <pathToUsb>`합니다.
7. 실행`Set-ExecutionPolicy -ExecutionPolicy Unrestricted`
8. 실행`.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
3. USB 드라이브를 제거한 다음 다음을 실행 하 여 장치를 종료 합니다.`shutdown -s -t 0`

>[!IMPORTANT]
>사용자의 등록을 완료할 때까지 대상 장치에 다시 전원을 공급 하지 마십시오. 

>[!NOTE]
>편의상이 CSV 파일의 [서식 파일](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx) 을 다운로드할 수 있습니다.

샘플 1과 **정확히 같은 열 머리글** 을 포함 해야 하지만 (제조업체, 모델 등), 다른 행에 대 한 고유한 데이터를 포함할 수 있습니다. 서식 파일을 사용 하는 경우 메모장 등의 텍스트 편집 도구에서이 템플릿을 열고 행 2와 아래에 데이터만 입력 하는 것이 좋습니다. 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,dGhpc2RldmljZWlzYW5tbWRkZXZpY2U
  
  
  ```

>[!NOTE]
>예제 데이터를 변경 하는 것을 잊은 경우에는 등록이 실패 합니다.   


## <a name="register-devices-by-using-the-azure-portal"></a>Azure Portal을 사용 하 여 장치 등록

Microsoft Managed Desktop [Azure Portal](https://aka.ms/mmdportal)의 왼쪽 탐색 창에서 **장치** 를 선택 합니다. **+ 장치 등록**을 선택 합니다. 날아오기는 다음과 같이 열립니다.

[![레지스터 장치를 선택한 후 날아오기](images/register-devices-flyin-sterile.png)](images/register-devices-flyin-sterile.png)


[//]: # (Sadly이는 그렇지 않습니다. 이 노트를 제거할 수는 있지만,이 정보를 다시 한 번에 채팅할 때까지 계속 남아 있습니다.)

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


다음 단계를 따릅니다.

1. **파일 업로드**에서 이전에 만든 CSV 파일의 경로를 제공 합니다.
2. 원하는 경우 사용자의 추적 목적으로 **주문 id** 또는 **구매 ID** 를 추가할 수 있습니다. 이러한 값에 대 한 형식 요구 사항은 없습니다.
3. **장치 등록**을 선택 합니다. 시스템은 장치를 디바이스 **블레이드에서**장치 목록에 추가 하 고 **등록 보류 중**으로 표시 합니다. 등록은 일반적으로 10 분 미만이 걸리고, 성공적인 장치는 **사용자가** 사용할 준비가 된 것으로 표시 되 고 최종 사용자가 사용을 시작할 때까지 기다릴 수 있습니다.


기본 **Microsoft Managed Desktop-Devices** 페이지에서 장치 등록의 진행 상태를 모니터링할 수 있습니다. 다음과 같은 가능한 상태가 보고 됩니다.

| 시/도 | 설명 |
|---------------|-------------|
| 등록 보류 중 | 등록이 아직 완료 되지 않았습니다. 나중에 다시 확인 합니다. |
| 등록 실패 | 등록을 완료할 수 없습니다. 자세한 내용은 [문제 해결](register-devices-self.md#troubleshooting) 을 참조 하세요. |
| 사용자 준비 | 등록을 완료 했으며 이제 장치를 최종 사용자에 게 배달할 준비가 되었습니다. Microsoft Managed Desktop은 처음 설정할 때 가이드를 제공 하므로 추가 준비를 수행할 필요가 없습니다. |
| 활성 | 장치가 최종 사용자에 게 배달 되었으며 테 넌 트에 등록 되어 있습니다. 또한 장치를 정기적으로 사용 하는 것을 나타냅니다. |
| 있었던 | 장치가 최종 사용자에 게 배달 되었으며 테 넌 트에 등록 되어 있습니다. 그러나 최근에 최근 7 일 이내에 장치를 사용 하지 않았습니다.  | 


## <a name="register-devices-by-using-an-api"></a>API를 사용 하 여 장치 등록

REST API를 사용 하 여 더 많은 유연성과 repeatability을 사용 하 여 여러 장치를 등록할 수 있습니다. 현재 API를 사용 하려면 Microsoft 연락처에서이 기능의 미리 보기에 참여 하도록 도움을 요청 하세요.



## <a name="troubleshooting"></a>문제 해결

| 오류 메시지 | 세부 정보 |
|---------------|-------------|
| 장치를 찾을 수 없음 | 제공 된 제조업체, 모델 또는 일련 번호에 대해 일치 하는 항목을 찾을 수 없기 때문에이 장치를 등록할 수 없습니다. 장치 공급자에서 이러한 값을 확인 합니다. |
| 장치를 찾을 수 없음 | 이 디바이스가 조직에 없으므로 등록을 취소할 수 없습니다. 추가 작업이 필요 하지 않습니다. |
| 하드웨어 해시가 잘못 되었습니다. | 이 장치에 대해 제공한 하드웨어 해시가 올바르게 포맷 되지 않았습니다. 하드웨어 해시를 두 번 확인 한 다음 다시 제출 합니다. |
| 장치가 이미 등록 됨 | 이 장치는 이미 조직에 등록 되어 있습니다. 추가 작업이 필요 하지 않습니다. |
| 다른 조직에서 요구 하는 장치 | 이 장치는 다른 조직에서 이미 요구 되었습니다. 장치 공급자에 게 문의 하세요. |
| 예기치 않은 오류 | 요청을 자동으로 처리할 수 없습니다. 지원 서비스에 문의 하 여 요청 ID를 제공 합니다.<requestId> |




