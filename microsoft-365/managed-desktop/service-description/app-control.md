---
title: 앱 제어
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 32ed3f95ebb4299796c5ad3eb71802c949701b65
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289130"
---
# <a name="app-control"></a>앱 제어

앱 컨트롤은 클라이언트 장치에서 코드를 실행 하는 것을 제한 하는 Microsoft Managed Desktop의 선택적 보안 방법입니다. 이 컨트롤은 고객이 승인한 게시자 목록에 의해 서명 된 코드만 실행할 수 있도록 요구 하 여 맬웨어 또는 악성 스크립트의 위험을 완화 합니다. 이 컨트롤은 다양 한 보안 이점을 제공 하지만, 주로 클라이언트 기반 익스플로잇 으로부터 데이터 및 id를 보호 하는 데 목적이 있습니다.

Microsoft Managed Desktop은 핵심 생산성 시나리오를 가능 하 게 하는 기본 정책을 만들어 앱 제어 정책 관리를 간소화 합니다. 해당 환경의 앱 및 스크립트와 관련 된 추가 서명자에 대 한 신뢰를 확장할 수 있습니다. 


모든 보안 기술에는 사용자 환경, 보안 및 비용 간의 균형이 필요 합니다. 앱 컨트롤을 사용 하면 환경에서 악성 소프트웨어의 위협을 줄일 수 있지만 사용자 및 IT 관리자를 위한 추가 작업에 대 한 결과가 표시 됩니다.

**추가 보안:**

앱 제어 정책에서 신뢰 하지 않는 앱 또는 스크립트가 장치에서 실행 되지 않도록 차단 됩니다.

**추가 책임:**

- 응용 프로그램 제어 정책에 의해 차단 되는지 여부를 확인 하기 위해 앱을 테스트할 책임이 있습니다.
- 앱이 차단 되는 경우에는 필요한 서명자 정보를 식별 하 고 관리 포털을 통해 변경을 요청 해야 합니다.

**Microsoft Managed Desktop 역할:**

- Microsoft Managed Desktop은 M365 앱, Windows, 팀, OneDrive 등의 핵심 Microsoft 제품을 사용할 수 있도록 하는 기본 정책을 유지 관리 합니다.
- Microsoft Managed Desktop 신뢰할 수 있는 서명자를 삽입 하 고 업데이트 된 정책을 장치에 배포 합니다.


## <a name="managing-trust-in-applications"></a>응용 프로그램의 신뢰 관리

Microsoft Managed Desktop은 Microsoft 기술의 핵심 구성 요소를 신뢰 하는 기본 정책을 curates 것입니다. 그런 다음 Microsoft Managed Desktop에 이미 믿을 수 있는 사용자를 알려 서 자신의 응용 프로그램 및 스크립트에 대 한 트러스트를 *추가* 합니다.

### <a name="base-policy"></a>기본 정책

Microsoft Managed Desktop, Microsoft cybersecurity 전문가와 공동 작업을 수행 하면 코드 컴파일 또는 신뢰할 수 없는 파일 실행과 같은 위험한 활동을 차단 하면서 Microsoft Intune을 통해 배포 되는 대부분의 앱을 사용할 수 있도록 하는 표준 정책을 만들고 유지 관리 합니다.

기본 정책은 소프트웨어 실행을 제한 하는 다음과 같은 접근 방식을 사용 합니다.

- 관리자가 실행 한 파일을 실행할 수 있습니다.
- 사용자가 쓸 수 없는 디렉터리에 *없는* 위치에 있는 파일은 실행이 허용 됩니다.
- [신뢰할 수 있는 서명자](#signer-requests)가 파일에 서명 합니다.
- Microsoft에서 서명한 대부분의 파일은 실행 되지만, 코드 컴파일과 같은 높은 위험 작업을 방지 하기 위해 일부는 차단 됩니다.


관리자가 아닌 사용자가 앱 또는 스크립트를 장치에 추가 했을 수 있습니다 (즉, 사용자가 쓰기 가능한 디렉터리에 있는 경우). 관리자가 이미 특별히 허용한 경우가 아니면 실행할 수 없습니다. 사용자가 맬웨어 설치를 tricked 하는 경우, 사용자가 실행 하는 앱의 취약성으로 인해 맬웨어가 설치 하려고 하거나, 사용자가 고의로 허용 되지 않은 앱 이나 스크립트를 실행 하려고 하면 정책 실행이 중지 됩니다.

### <a name="signer-requests"></a>서명자 요청

*서명자 요청*을 관리 하 여 신뢰할 수 있는 소프트웨어 공급 업체에서 제공 하는 앱을 알려 줍니다. 이렇게 하면 해당 신뢰 정보가 기본 응용 프로그램 제어 정책에 추가 되 고 해당 게시자의 인증서로 서명 된 모든 소프트웨어가 장치에서 실행 될 수 있습니다.

## <a name="audit-and-enforced-policies"></a>감사 및 적용 정책

Microsoft Managed Desktop은 두 가지 Microsoft Intune 정책을 사용 하 여 앱 제어권을 제공 합니다.

### <a name="audit-policy"></a>감사 정책
이 정책은 앱 또는 스크립트가 적용 된 정책에 의해 차단 되는지 여부를 기록 하는 로그를 만듭니다. 감사 정책은 앱 제어 규칙을 적용 하지 않으며 응용 프로그램에 게시자 예외가 필요한 지 여부를 확인 하기 위한 테스트 목적으로 사용 됩니다. 지정 된 앱 또는 스크립트의 실행 또는 설치를 차단 하는 대신 이벤트 뷰어에 경고 (8003 또는 8006 이벤트)를 기록 합니다.

### <a name="enforced-policy"></a>적용 정책
이 정책은 앱 또는 스크립트가 차단 될 때마다 트러스트 되지 않은 앱 및 스크립트를 실행 하 고 로그를 만들 수 없도록 차단 합니다. 적용 된 정책에 의해 표준 사용자는 사용자가 쓰기 가능한 디렉터리에 저장 되어 있는 앱 이나 스크립트를 실행할 수 없습니다.

테스트 그룹의 장치에는 감사 정책이 적용 되므로 응용 프로그램에서 문제를 발생 시킬 것인지 여부를 확인 하는 데 사용할 수 있습니다. 다른 모든 그룹 (첫째, 빠르게, 광범위 함)은 적용 되는 정책을 사용 하므로 해당 그룹의 사용자는 신뢰할 수 없는 앱 이나 스크립트를 실행 하지 못할 수도 있습니다.







