---
title: AutoPilot 장치 오류 문제 해결
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: Microsoft 365 Business Premium에서 AutoPilot 장치 파일로 작업하는 동안 발생할 수 있는 오류를 해결하는 방법을 설명하는 방법을 확인합니다.
ms.openlocfilehash: bec5126696ee322db42e4b7c5cd8e0df485ab2c9
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403413"
---
# <a name="troubleshoot-autopilot-device-errors"></a>AutoPilot 장치 오류 문제 해결

## <a name="device-file-error-messages"></a>장치 파일 오류 메시지

다음은 Microsoft 365 Business Premium에서 AutoPilot 장치 파일로 작업하는 동안 발생할 수 있는 몇 가지 오류에 대한 정보입니다. 
  
|**오류 코드**|**해결 방법**|
|:-----|:-----|
|잘못된 요청 본문  <br/> |이 오류는 거의 발생하지 않습니다. 이 오류가 표시된 경우 작업을 다시 시도하십시오.  <br/> |
|장치에 대한 하드웨어 해시 값이 정확하지 않습니다.  <br/> |이 오류가 표시될 경우 한 장치의 하드웨어 해시에 대해 CSV 파일에서 제공한 값이 올바를 수 없습니다. 먼저 값이 올바르게 입력되지 않은지 확인합니다. 값이 정확하지만 이 오류가 계속 발생하고 있는 경우 하드웨어 공급업체에 도움을 요청하십시오.  <br/> |
|다른 테넌트에 할당된 장치  <br/> |이 오류가 표시될 경우 CSV 파일에서 제공한 일련 번호 또는 하나 이상의 디바이스의 제품 키가 잘못되었습니다. 먼저 값이 올바르게 입력되지 않은지 확인합니다. 값이 정확하지만 이 오류가 계속 발생하고 있는 경우 하드웨어 공급업체에 도움을 요청하십시오.  <br/> |
|CSV 파일에 잘못된 일련 번호 또는 제품 키가 포함되어 있습니다.  <br/> |이 오류가 표시되어 등록하려는 장치가 이미 다른 조직에 의해 등록되어 있는 것입니다. 이 오류를 해결하기 위해 하드웨어 공급업체에 도움을 요청합니다.  <br/> |
|이 장치는 AutoPilot을 사용하여 설치에 지원되지 않습니다.  <br/> | 이 오류는 장치가 AutoPilot 배포 요구 사항을 충족하지 않는다는 의미입니다. 장치가 다음 요구 사항을 충족해야 합니다.  <br/>  Windows 10 버전 1703 이상  <br/>  Windows에서 바로 사용할 수 있는 환경을 통과하지 않은 새 디바이스입니다.  <br/> |
|디바이스를 찾을 수 없습니다.  <br/> |이 오류는 CSV 파일의 하나 이상의 장치가 조직에 등록되지 않은 것을 의미합니다. 이 문제를 해결하기 위해 하드웨어 공급업체에 도움을 요청합니다.  <br/> |
