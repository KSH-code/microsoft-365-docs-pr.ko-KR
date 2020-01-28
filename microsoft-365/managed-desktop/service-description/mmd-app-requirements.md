---
title: Microsoft Managed Desktop 응용 프로그램 요구 사항
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: fd19764ab164373cee1de088ea402b3c46b61b81
ms.sourcegitcommit: 03a83ff76c8162b850c4c552759c49f2a4750574
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/26/2020
ms.locfileid: "41558575"
---
# <a name="microsoft-managed-desktop-app-requirements"></a>Microsoft Managed Desktop 응용 프로그램 요구 사항

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreement for MMD. do not delete.-->

<!--Application addendum -->
 
Microsoft Managed Desktop 장치에 대 한 성능, 안정성 및 서비스 용이성을 보장 하기 위해 고객의 lob 앱은 최종 사용자 환경에 심각한 영향을 주지 않거나 보안 태세를 수정 하지 않아야 합니다. 따라서 Microsoft Managed Desktop 장치에 배포 하려는 기간 업무 (lob) 응용 프로그램은이 항목의 요구 사항을 충족 해야 합니다.

## <a name="application-condition"></a>응용 프로그램 조건

응용 프로그램이 Microsoft Managed Desktop 환경에 악영향을 미치지 않는 것이 중요 합니다. 응용 프로그램에서 배포 하기 위해 충족 해야 하는 요구 사항은 다음과 같습니다. 지정 된 응용 프로그램 또는 드라이버의 경우 Microsoft는 여기에 제공 된 모든 요구 사항을 waive 수 있습니다. Microsoft는 Microsoft 관리 데스크톱 장치의 성능 및 안정성에 부정적인 영향을 주는 응용 프로그램 또는 드라이버를 제거 하는 것을 결정할 수 있습니다.

## <a name="centrally-managed-apps"></a>중앙 집중식으로 관리 되는 앱

Microsoft 관리 장치에 설치 된 모든 응용 프로그램 및 드라이버는 Microsoft Intune, Microsoft Store 또는 비즈니스용 Microsoft Store를 통해 배포 해야 합니다. 사용 가능한 경우 Windows Update 서비스를 통해 드라이버도 배포 됩니다. 

## <a name="prohibited-app-classes"></a>금지 되는 앱 클래스

특정 응용 프로그램 유형은 Microsoft Managed Desktop 장치에서 허용 되지 않습니다.
- 타사 바이러스 백신, 보안 또는 감사 소프트웨어
- Office 365 ProPlus 이전 버전의 Microsoft Office
- 다른 타사 소프트웨어를 설치 하거나 번들 하는 응용 프로그램

## <a name="restricted-app-behaviors"></a>제한 된 앱 동작

특정 앱 동작은 사용자 환경에 부정적인 영향을 주거나 Microsoft 관리 되는 데스크톱 장치에 보안 위험을 줄 수 있습니다. 다음 동작이 적용 되는 앱은 microsoft와 관련 없는 Microsoft Managed Desktop environment에서 실행할 수 없습니다.

사용자 환경:
- 백그라운드 서비스 설치
- Windows 시작 경로에 자신 추가
- 드라이버에 종속 된 응용 프로그램
- 타사 웹 브라우저

보안:
- 최종 사용자의 권한 상승
- 앱 스토어 역할을 하거나 기본 제공 확장 관리자를 사용 합니다.
- 알려진 보안 취약성
- 최종 사용자 데이터에 대 한 액세스 암호화 또는 제한
- 서명 되지 않았거나 신뢰할 수 있는 루트에 롤업 하지 않는 인증서를 사용 하 여 서명 됨


## <a name="driver-deployment"></a>드라이버 배포

Microsoft Managed Desktop은 Microsoft 관리 장치를 사용 하 여 Windows Update 또는 설치 된 받은 편지함을 통해 제공 되는 장치 드라이버만 지원 합니다. 

응용 프로그램에서 실행 해야 하는 특정 드라이버가 필요한 경우에는 제한 된 응용 프로그램으로 간주 되므로를 Microsoft Managed Desktop에 배포 해야 합니다. 

