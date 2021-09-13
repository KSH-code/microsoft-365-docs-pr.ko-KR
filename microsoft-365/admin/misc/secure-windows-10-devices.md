---
title: Windows 10 장치 보안
f1.keywords:
- CSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- O365E_BCSSetup4WindowsConfig
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ROBOTS: NO INDEX, NO FOLLOW
ms.assetid: 21e5551f-fa35-4f13-9418-f80d668b6a2b
description: 자신의 직장 또는 학교 계정에 로그인할 때 모든 Windows 10 기본 장치 정책의 설정을 구성하는 방법을 학습합니다.
ms.openlocfilehash: b4460f8f5e40ee6f0e121b128f17e27db7aa4979
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59186956"
---
# <a name="secure-windows-10-devices"></a>Windows 10 장치 보안

이 문서는 이 문서에 Microsoft 365 Business Premium.

여기서 구성하는 설정은 Windows 10의 기본 장치 정책에 해당합니다. 모바일 장치 및 PC를 포함하여 Windows 10 계정으로 로그인하여 디바이스를 연결하는 모든 사용자는 이러한 설정을 자동으로 받게 됩니다. 설치 중에 기본 정책을 수락하고 특정 사용자 그룹을 대상으로 하는 정책은 나중에 추가하는 것이 권장됩니다.
  
## <a name="settings-to-secure-windows-10-devices"></a>Windows 10 장치의 보안 설정

모든 설정은 기본적으로 **켜짐** 으로 되어 있습니다. 다음과 같은 설정을 사용할 수 있습니다.
  


|설정  <br/> |설명  <br/> |
|:-----|:-----|
|Windows Defender Antivirus를 사용하여 바이러스 및 기타 위협으로부터 PC를 보호하도록 지원  <br/> |인터넷에 연결하여 발생할 수 있는 위험으로부터 PC를 보호하기 위해 Windows Defender Antivirus가 켜져 있어야 합니다.  <br/> |
|Microsoft Edge에서 웹 기반 위협으로부터 PC를 보호하도록 지원  <br/> |Edge에서 사용자를 악성 사이트와 다운로드로부터 보호하는 설정을 켭니다.  <br/> |
|BitLocker를 사용하여 PC의 파일 및 폴더를 무단 액세스로부터 보호  <br/> |Bitlocker는 컴퓨터 하드 드라이브를 암호화하여 데이터를 보호하고, 컴퓨터가 분실되거나 도난당한 경우 데이터 노출을 방지합니다. 자세한 내용은 [Bitlocker FAQ 를 참조하세요.](/windows/security/information-protection/bitlocker/bitlocker-frequently-asked-questions)  <br/> |
|이 시간 동안 유휴 상태일 때 장치 화면 끄기  <br/> |사용자가 유휴 상태일 때 회사 데이터가 안전하게 보호되도록 합니다. 사용자가 커피숍과 같은 공공장소에서 작업하다가 잠시 자리를 비우거나 다른 곳에 주의를 기울인 순간 장치가 타인들의 시선에 노출될 수 있습니다. 이 설정은 사용자가 얼마 동안 유휴 상태이면 화면이 꺼지는지 지정합니다.  <br/> |
|