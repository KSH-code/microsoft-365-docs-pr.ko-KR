---
title: 장치 목록 CSV-파일
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 932e3676-2491-49f0-9177-d893d2f5276e
ROBOTS: NOINDEX
description: AutoPilot 용 CSV 파일을 Microsoft 365에서 비즈니스용으로 만드는 방법에 대해 알아봅니다.
ms.openlocfilehash: b1154d639ba23180f637520750d94f00e997cfc4
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627863"
---
# <a name="device-list-csv-file"></a>장치 목록 CSV-파일

## <a name="device-list-csv-file-format"></a>장치 목록 .csv 파일 형식

Windows Autopilot를 통해 장치를 관리 하 고 배포 하려면 장치에 대 한 특정 정보가 포함 된 .csv 파일이 필요 합니다.
  
장치 목록 파일의 열에는 지정 된 순서 대로 다음과 같은 헤더가 있어야 합니다.
  
- A 열: 장치 일련 번호

- B 열: 비워 둠

- C 열: 하드웨어 해시

하드웨어 공급업체로부터 이 정보를 얻거나 CSV 파일을 생성하는 [Get-WindowsAutoPilotInfo PowerShell 스크립트](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo)를 사용할 수 있습니다. 

장치를 추가할 때는 프로필에도 추가 해야 합니다. 프로필은 AutoPilot 배포 프로필을 장치 또는 장치 그룹에 적용 하는 데 사용 됩니다.
  
## <a name="related-articles"></a>관련 문서

[비즈니스 설명서 및 리소스에 대 한 Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[Microsoft 365 for business 시작](https://support.office.com/article/496e690b-b75d-4ff5-bf34-cc32905d0364)
  
[비즈니스에 대 한 Microsoft 365 관리](https://support.office.com/article/27ff1678-865a-4707-8145-e1155aa815d6)
  
