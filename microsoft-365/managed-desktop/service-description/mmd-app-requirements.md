---
title: Microsoft Managed Desktop 응용 프로그램 요구 사항
description: ''
keywords: microsoft Managed Desktop, microsoft 365, 서비스, 설명서
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/08/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: de6cc7d77e023a9d41961e5fbcce060f1bb659ae
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278338"
---
# <a name="microsoft-managed-desktop-app-requirements"></a>Microsoft Managed Desktop 응용 프로그램 요구 사항

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreeement for MMD. do not delete.-->

<!--Application addendum -->
 
Microsoft Managed Desktop 장치에 배포 하려는 기간 업무 (lob) 응용 프로그램은이 항목의 요구 사항을 충족 해야 합니다. 

## <a name="application-condition"></a>응용 프로그램 조건

응용 프로그램이 Microsoft Managed Desktop 환경에 악영향을 미치지 않는 것이 중요 합니다. 다음은 Microsoft에서 배포 하기 위해 응용 프로그램에서 충족 해야 하는 요구 사항입니다. 지정 된 응용 프로그램 또는 드라이버의 경우 Microsoft는 여기에 제공 된 모든 요구 사항을 waive 수 있습니다. microsoft는 microsoft 관리 데스크톱 장치의 성능 및 안정성에 부정적인 영향을 주는 응용 프로그램 또는 드라이버를 제거 하는 것을 결정할 수 있습니다.

## <a name="deployable-using-microsoft-technologies"></a>Microsoft 기술을 사용 하 여 배포 가능

microsoft Managed Desktop은 Intune, microsoft store 및 비즈니스용 microsoft store를 사용 하 여 응용 프로그램을 배포 합니다. 따라서 응용 프로그램은 해당 서비스의 최신 버전을 통해 배포할 수 있는 방식으로 패키지 되어야 합니다.

## <a name="prohibited-app-classes"></a>금지 되는 앱 클래스

특정 응용 프로그램 유형은 Microsoft Managed Desktop 장치에서 허용 되지 않습니다.
- 타사 바이러스 백신, 보안 또는 감사 소프트웨어
- 타사 웹 브라우저
- Office 365 Pro Plus 이전 버전의 Microsoft Office
- 다른 타사 소프트웨어를 설치 하거나 번들 하는 응용 프로그램

## <a name="restricted-app-behaviors"></a>제한 된 앱 동작

특정 응용 프로그램 동작은 사용자 환경에 부정적인 영향을 주거나 Microsoft 관리 되는 데스크톱 장치에 보안 위험을 제공할 수 있습니다. 응용 프로그램에는 다음과 같은 동작이 나 특성이 나타나지 않습니다. 

사용자 환경:
- 백그라운드 서비스 설치 또는 오랫동안 실행 되는 백그라운드 프로세스 생성
- Windows 시작 경로에 자신 추가

보안:
- 문서화 되지 않은 windows 또는 office api를 호출 하거나 내부 Windows 또는 office 데이터 구조에 대 한 종속성을 사용 합니다.
- 앱 저장소 역할을 하거나 기본 제공 확장 관리자를 사용 합니다.
- 최종 사용자의 권한 상승
- 알려진 보안 취약성
- 신뢰할 수 있는 루트에 롤업 하지 않는 인증서를 사용 하 여 서명 됨
- 최종 사용자 데이터에 대 한 액세스 암호화 또는 제한
- 런타임에 운영 체제 코드 수정

## <a name="driver-deployment"></a>드라이버 배포

windows Update에서 드라이버를 사용할 수 없거나 windows 하드웨어 품질 실습 (WHQL)에서 별도로 서명 하지 않은 경우 microsoft에서 microsoft Managed Desktop 장치에 드라이버를 배포 하기 전에 드라이버를 승인 해야 합니다.
