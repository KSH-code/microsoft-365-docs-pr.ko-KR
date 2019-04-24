---
title: AutoPilot 장치 오류 문제 해결
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: troubleshooting
f1_keywords:
- ZTDTroubleshootDeviceErrors
- O365E_ZTDTroubleshootDeviceErrors
- BCS365_ZTDTroubleshootDeviceErrors
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: AutoPilot 장치 파일 오류 문제를 해결 하는 방법을 알아봅니다.
ms.openlocfilehash: 9d4a47f78c38d8c076f5b3876a36b6bf46eaaaf3
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32279841"
---
# <a name="troubleshoot-autopilot-device-errors"></a>AutoPilot 장치 오류 문제 해결

## <a name="device-file-error-messages"></a>장치 파일 오류 메시지

Microsoft 365 Business에서 AutoPilot 장치 파일을 사용 하 여 작업 하는 동안 표시 될 수 있는 몇 가지 오류에 대 한 정보는 다음과 같습니다. 
  
|**오류 코드**|**해결 방법**|
|:-----|:-----|
|요청 본문이 잘못 됨  <br/> |이 오류가 표시 되는 경우는 거의 발생 하지 않는 경우에는 작업을 다시 시도 하십시오.  <br/> |
|장치에 대 한 하드웨어 해시 값이 올바르지 않습니다.  <br/> |이 오류가 표시 되 면 한 장치의 하드웨어 해시에 대해 CSV 파일에 제공한 값이 잘못 되었음을 의미 합니다. 먼저 값을 올바르게 입력 했는지 확인 합니다. 값이 올바르지만이 오류가 여전히 발생 하는 경우에는 하드웨어 공급 업체에 도움을 요청 하세요.  <br/> |
|다른 테 넌 트에 할당 된 장치  <br/> |이 오류가 표시 되는 경우에는 CSV 파일에서 하나 이상의 장치에 대 한 일련 번호나 제품 키에 제공한 값이 올바르지 않음을 의미 합니다. 먼저 값을 올바르게 입력 했는지 확인 합니다. 값이 올바르지만이 오류가 여전히 발생 하는 경우에는 하드웨어 공급 업체에 도움을 요청 하세요.  <br/> |
|CSV 파일에 잘못 된 일련 번호 또는 제품 키가 포함 되어 있습니다.  <br/> |이 오류가 표시 되는 경우 등록을 tyring 하는 장치가 다른 조직에서 이미 등록 된 것입니다. 이 문제를 해결 하려면 하드웨어 공급 업체에 도움을 요청 하세요.  <br/> |
|AutoPilot을 사용 하 여 설치를 지원 하지 않는 장치입니다.  <br/> | 이 오류는 장치가 AutoPilot 배포 요구 사항을 충족 하지 않음을 의미 합니다. 장치가 다음 요구 사항을 충족해야 합니다.  <br/>  Windows 10 버전 1703 이상  <br/>  Windows 첫 실행 경험을 완료하지 않은 새 장치  <br/> |
|장치를 찾을 수 없음  <br/> |이 오류는 CSV 파일에 있는 하나 이상의 장치가 조직에 등록 되어 있지 않음을 의미 합니다. 이 문제를 해결 하려면 하드웨어 공급 업체에 도움을 요청 하세요.  <br/> |
   
