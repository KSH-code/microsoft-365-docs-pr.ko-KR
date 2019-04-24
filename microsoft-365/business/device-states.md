---
title: 장치 상태
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c3ac23c5-d4b4-4b1b-b7ce-ea759521bf8c
description: Microsoft 365 Business의 장치 상태에 대해 알아봅니다.
ms.openlocfilehash: 15114835a5014f5bfac600eac79bcdffdaec481a
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32276987"
---
# <a name="device-states"></a>장치 상태

## <a name="device-states"></a>장치 상태

**장치 작업** 목록(관리 홈 \> **장치 작업**)의 장치는 다음 상태를 가질 수 있습니다.
  
![In the Device actions list, you can see the Devices states.](media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|**상태**|**설명**|
|:-----|:-----|
|Intune에서 관리  <br/> |Microsoft 365 Business에 의해 관리됩니다.  <br/> |
|사용 중지 보류 중  <br/> |Microsoft 365 Business가 장치에서 회사 데이터를 제거하기 위해 준비 중입니다.  <br/> |
|사용 중지 진행 중  <br/> |Microsoft 365 Business가 현재 장치에서 회사 데이터를 제거 중입니다.  <br/> |
|사용 중지 실패  <br/> | 회사 데이터 제거 작업이 실패했습니다.  <br/> |
|사용 중지 취소됨  <br/> |사용 중지 작업이 취소되었습니다.  <br/> |
|초기화 보류 중  <br/> |초기화를 시작하기 위해 대기 중입니다.  <br/> |
|초기화 진행 중  <br/> |초기화가 실행되었습니다.  <br/> |
|초기화 실패  <br/> |초기화를 수행할 수 없습니다.  <br/> |
|초기화 취소됨  <br/> |초기화가 취소되었습니다.  <br/> |
|비정상  <br/> |작업이 보류 중(또는 진행 중)이지만, 장치가 30 이상 체크 인하지 않았음을 의미합니다.  <br/> |
|삭제 보류 중  <br/> |삭제 작업이 보류 중입니다.  <br/> |
|검색됨  <br/> |Microsoft 365 Business가 장치를 검색했습니다.  <br/> |
   
