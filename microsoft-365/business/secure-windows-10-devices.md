---
title: Windows 10 장치 보안
f1.keywords:
- CSH
ms.author: sirkkuw
author: sirkkuw
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
ms.assetid: 21e5551f-fa35-4f13-9418-f80d668b6a2b
description: 회사 또는 학교 계정에 로그인 할 때 Windows 10 장치에서 수신 하는 기본 장치 정책의 설정을 구성 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: b586e687d6b61873b77fac8586396ab51fd90b9b
ms.sourcegitcommit: 90efec455336b4cecc06a8cbf0ce287740433523
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2020
ms.locfileid: "46898071"
---
# <a name="secure-windows-10-devices"></a>Windows 10 장치 보안

이 문서는 Microsoft 365 Business Premium에 적용 됩니다.

여기서 구성하는 설정은 Windows 10의 기본 장치 정책에 해당합니다. 모바일 장치 및 Pc를 포함 하 여 Windows 10 장치에 연결 하는 모든 사용자에 게는 해당 작업 계정으로 로그인 하 여 자동으로 이러한 설정이 수신 됩니다. 설치 중에 기본 정책을 수락하고 특정 사용자 그룹을 대상으로 하는 정책은 나중에 추가하는 것이 권장됩니다.
  
## <a name="settings-to-secure-windows-10-devices"></a>Windows 10 장치의 보안 설정

모든 설정은 기본적으로 **켜짐**으로 되어 있습니다. 다음과 같은 설정을 사용할 수 있습니다.
  
|||
|:-----|:-----|
|설정  <br/> |설명  <br/> |
|Windows Defender Antivirus를 사용하여 바이러스 및 기타 위협으로부터 PC를 보호하도록 지원  <br/> |인터넷에 연결하여 발생할 수 있는 위험으로부터 PC를 보호하기 위해 Windows Defender Antivirus가 켜져 있어야 합니다.  <br/> |
|Microsoft Edge에서 웹 기반 위협으로부터 PC를 보호하도록 지원  <br/> |Edge에서 사용자를 악성 사이트와 다운로드로부터 보호하는 설정을 켭니다.  <br/> |
|이 시간 동안 유휴 상태일 때 장치 화면 끄기  <br/> |사용자가 유휴 상태일 때 회사 데이터가 안전하게 보호되도록 합니다. 사용자가 커피숍과 같은 공공장소에서 작업하다가 잠시 자리를 비우거나 다른 곳에 주의를 기울인 순간 장치가 타인들의 시선에 노출될 수 있습니다. 이 설정은 사용자가 얼마 동안 유휴 상태이면 화면이 꺼지는지 지정합니다.  <br/> |
|사용자가 Microsoft Store에서 앱을 다운로드할 수 있도록 허용  <br/> |사용자가 Microsoft Store에서 앱을 다운로드하여 설치할 수 있도록 허용합니다. 앱에는 게임에서 생산성 도구에 이르기까지 다양한 종류가 있습니다. 따라서 기본값은 **켜기**이지만 관리자가 보안을 위해 끌 수 있습니다.  <br/> |
|