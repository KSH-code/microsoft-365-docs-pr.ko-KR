---
title: 장치 목록 CSV-file
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 932e3676-2491-49f0-9177-d893d2f5276e
ROBOTS: NOINDEX
description: 비즈니스용 앱의 AutoPilot에 대한 CSV Microsoft 365 방법을 학습합니다.
ms.openlocfilehash: bc67e32d834ec8fde13386fb02ef1368ca3757cef47e78575d00a3e3d2fc6db3
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "53824122"
---
# <a name="device-list-csv-file"></a>장치 목록 CSV-file

## <a name="device-list-csv-file-format"></a>장치 목록 .csv 파일 형식

Autopilot을 통해 디바이스를 Windows 배포하려면 장치에 대한 특정 .csv 포함하는 .csv 파일이 필요합니다.
  
장치 목록 파일의 열에는 지정된 순서대로 다음 헤더가 있어야 합니다.
  
- A 열: 장치 일련 번호

- B 열: 비워 두기

- C 열: 하드웨어 해시

하드웨어 공급업체로부터 이 정보를 얻거나 CSV 파일을 생성하는 [Get-WindowsAutoPilotInfo PowerShell 스크립트](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo)를 사용할 수 있습니다. 

디바이스를 추가할 때 프로필에도 추가해야 합니다. 프로필은 장치 또는 장치 그룹에 AutoPilot 배포 프로필을 적용하는 데 사용됩니다.
  
## <a name="related-articles"></a>관련 문서

[Microsoft 365 문서 및 리소스에 대한 자세한 설명](../../business/index.yml)
  
[비즈니스용 Microsoft 365 시작](../../business/microsoft-365-business-overview.md)
  
[비즈니스 Microsoft 365 관리](../../business/manage.md)
