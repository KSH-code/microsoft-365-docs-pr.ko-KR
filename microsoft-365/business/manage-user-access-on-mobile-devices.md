---
title: 사용자가 모바일 장치에서 Office 문서에 액세스하는 방법 관리
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- O365E_BCSSetup4OfficeMobile
ms.service: o365-administration
localization_priority: Normal
ms.collection:
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
ms.assetid: aa31319c-9196-48c9-a90b-4057e0494c7a
description: 모바일 장치에서 Office 앱에 안전 하 게 액세스할 수 있도록 하는 보호 정책에 대해 알아봅니다.
ms.openlocfilehash: 39d28a3a78fb06d0020c484b1782b544f6a8c656
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41593824"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a>사용자가 모바일 장치에서 Office 문서에 액세스하는 방법 관리

 사용자가 모바일 장치에서 Office 파일을 액세스하는 방법을 제어하는 정책 설정은 기본적으로 **꺼짐**으로 되어 있습니다. 설치 중에 기본값을 사용 하 여 모든 사용자에 게 적용 되는 Android, iOS 및 Windows 10에 대 한 응용 프로그램 정책을 만드는 것이 좋습니다. 설치가 완료되면 추가로 정책을 만들 수 있습니다. 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a>사용자가 모바일 장치에서 Office 파일을 액세스하는 방법을 제어하는 설정

사용자가 Office 작업 파일을 액세스하는 방법을 관리할 때 다음과 같은 설정을 사용할 수 있습니다.
  
|||
|:-----|:-----|
|설정  <br/> |설명  <br/> |
|Office 앱 액세스에 PIN 또는 지문 필요  <br/> |이 설정이 설정 되어 있으면 사용자가 모바일 장치에서 Office **앱을 사용**하기 전에 다른 인증 형식 (사용자 이름 및 암호 추가)을 제공 해야 합니다.  <br/> |
|PIN을 재설정할 로그인 실패 횟수  <br/> |권한 없는 사용자가 PIN을 임의로 추측하는 것을 방지하기 위해 사용자가 지정한 횟수만큼 잘못된 PIN이 입력되면 PIN을 재설정합니다.  <br/> |
|Office 앱이 이 시간 동안 유휴 상태인 경우 사용자 다시 로그인 필요  <br/> |이 설정은 사용자가 다시 로그인 하 라는 메시지가 표시 될 때까지 유휴 상태일 수 있는 기간을 결정 합니다.  <br/> |
|탈옥 또는 루팅된 장치에서의 작업 파일 액세스 거부  <br/> |기술을 잘 아는 사용자들은 장치를 탈옥 또는 루팅하여 사용할 수 있습니다. 즉, 사용자가 운영 체제를 수정할 수 있기 때문에 장치가 맬웨어에 취약 해질 수 있습니다. 이 설정이 **켜기** 로 되어 있을 경우 이러한 장치는 차단됩니다.  <br/> |
|사용자가 Office 앱에서 개인 앱으로 콘텐츠를 복사 하도록 허용 하지 않음  <br/> |설정이 설정 되어 있으면 사용자가 작업 파일의 **정보를 개인**파일로 복사할 수 없습니다. 설정이 **해제**되어 있으면 사용자가 작업 파일의 정보를 개인 앱 또는 개인 계정으로 복사할 수 있습니다.  <br/> |
   

