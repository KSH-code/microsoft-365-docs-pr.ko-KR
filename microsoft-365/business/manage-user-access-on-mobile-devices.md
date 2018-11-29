---
title: 사용자가 모바일 장치에서 Office 문서에 액세스하는 방법 관리
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: overview
f1_keywords:
- 'O365E_BCSSetup4OfficeMobile '
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: aa31319c-9196-48c9-a90b-4057e0494c7a
description: 모바일 장치에서 Office 응용 프로그램에 대 한 보안 액세스 도움이 되는 보호 정책에 알아봅니다.
ms.openlocfilehash: 75dbe79acccabd851c43259a165e79bfe3c509c0
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870034"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a>사용자가 모바일 장치에서 Office 문서에 액세스하는 방법 관리

 사용자가 모바일 장치에서 Office 파일을 액세스하는 방법을 제어하는 정책 설정은 기본적으로 **꺼짐**으로 되어 있습니다. 설치 중에 기본값을 그대로 수락하여 모든 사용자에게 적용되도록 Android, iOS 및 Windows 10 응용 프로그램 정책을 생성하는 것이 권장됩니다. 설치가 완료되면 추가로 정책을 만들 수 있습니다. 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a>사용자가 모바일 장치에서 Office 파일을 액세스하는 방법을 제어하는 설정

사용자가 Office 업무 파일에 액세스하는 방법을 관리할 때 다음과 같은 설정을 사용할 수 있습니다.
  
|||
|:-----|:-----|
|설정  <br/> |설명  <br/> |
|Office 앱 액세스에 PIN 또는 지문 필요  <br/> |이 설정이 **켜짐**으로 되어 있으면 사용자는 사용자 이름 및 암호 외에 다른 인증 수단을 제공해야 모바일 장치에서 Office 앱을 사용할 수 있습니다.  <br/> |
|이 횟수만큼 로그인 실패 시 PIN 재설정  <br/> |권한 없는 사용자가 PIN을 임의로 추측하는 것을 방지하기 위해 사용자가 지정한 횟수만큼 잘못된 PIN이 입력되면 PIN을 재설정합니다.  <br/> |
|Office 앱이 이 시간 동안 유휴 상태인 경우 사용자 다시 로그인 필요  <br/> |사용자가 얼마 동안 유휴 상태이면 다시 로그인해야 하는지 지정합니다.  <br/> |
|탈옥 또는 루팅된 장치에서의 작업 파일 액세스 거부  <br/> |기술을 잘 아는 사용자들은 장치를 탈옥 또는 루팅하여 사용할 수 있습니다. 즉, 사용자가 운영 체제를 수정할 수 있기 때문에 장치가 맬웨어에 노출될 확률이 높아집니다. 이 설정이 **켜짐**으로 되어 있을 경우 이러한 장치는 차단됩니다.  <br/> |
|사용자가 Office 앱의 콘텐츠를 개인 앱으로 복사할 수 있도록 허용  <br/> |기본적으로 허용되는 설정입니다. 이 설정이 **켜짐**으로 되어 있으면 사용자가 업무 파일의 정보를 개인 파일로 복사할 수 있습니다. 이 설정이 **꺼짐**으로 되어 있으면 사용자가 업무 파일의 정보를 개인 앱 또는 개인 계정으로 복사할 수 없습니다.  <br/> |
   

