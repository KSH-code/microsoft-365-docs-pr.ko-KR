---
title: 앱 제어
description: 응용 프로그램 제어 및 신뢰를 사용하는 방법
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.openlocfilehash: 1a3b976accf1f86a96100efb9a890adab4ec3698
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60201556"
---
# <a name="app-control"></a>앱 제어

앱 제어는 클라이언트 장치에서 코드 Microsoft Managed Desktop 제한하는 선택적 보안 관행입니다. 이 컨트롤은 고객이 승인한 게시자 목록에서 서명한 코드만 실행할 수 있도록 하여 맬웨어 또는 악성 스크립트의 위험을 완화합니다. 이 컨트롤에는 많은 보안 이점이 있지만 주로 클라이언트 기반 악용으로부터 데이터 및 ID를 보호하는 것을 목표로 합니다.

Microsoft Managed Desktop 핵심 생산성 시나리오를 가능하게 하는 기본 정책을 만들어 앱 제어 정책 관리를 간소화합니다. 환경의 앱 및 스크립트와 관련이 있는 다른 서명자까지 신뢰를 확장할 수 있습니다. 


모든 보안 기술을 사용하려면 사용자 환경, 보안 및 비용의 균형을 유지해야 합니다. 앱 제어는 사용자 환경에서 악성 소프트웨어의 위협을 줄일 수 있지만, 사용자에게는 그에 대한 결과 및 IT 관리자를 위한 추가 작업이 있습니다.

**추가 보안:**

앱 제어 정책에서 신뢰하지 않는 앱 또는 스크립트는 장치에서 실행되지 못하게 차단됩니다.

**추가 책임:**

- 앱을 테스트하여 응용 프로그램 제어 정책에 의해 차단될지 여부를 식별할 책임이 있습니다.
- 앱이 차단되거나 차단된 경우 필요한 서명자 세부 정보를 식별하고 관리 포털을 통해 변경을 요청할 책임이 있습니다.

**Microsoft Managed Desktop 책임:**

- Microsoft Managed Desktop M365 앱, Windows, Teams, OneDrive 같은 핵심 Microsoft 제품을 사용할 수 있도록 하는 기본 정책을 유지 관리합니다.
- Microsoft Managed Desktop 서명을 삽입하고 업데이트된 정책을 장치에 배포합니다.


## <a name="managing-trust-in-applications"></a>응용 프로그램의 트러스트 관리

Microsoft Managed Desktop Microsoft 기술의 핵심 구성 요소를 신뢰하는 기본 정책을 구성합니다. 그런 *다음* 이미 신뢰하는 응용 프로그램 및 스크립트에 Microsoft Managed Desktop 신뢰를 추가합니다.

### <a name="base-policy"></a>기본 정책

Microsoft Managed Desktop Microsoft 사이버 보안 전문가와 협력하여 코드 컴파일 또는 보안되지 않은 파일의 실행과 같은 위험한 활동을 차단하면서 Microsoft Intune 통해 배포된 대부분의 앱을 사용할 수 있는 표준 정책을 만들고 유지 관리합니다.

기본 정책은 다음과 같은 방식으로 소프트웨어 실행을 제한합니다.

- 관리자가 실행한 파일은 실행할 수 있습니다.
- 사용자가 덮어 사용할 수 있는 *폴더에* 없는 위치에 있는 파일은 실행할 수 있습니다.
- 파일은 신뢰할 수 있는 [서명자 에 의해 서명됩니다.](#signer-requests)
- Microsoft에서 서명한 대부분의 파일은 실행됩니다. 그러나 코드 컴파일과 같은 고위험 작업을 방지하기 위해 일부 파일은 차단됩니다.


관리자 외의 사용자가 장치에 앱 또는 스크립트를 추가할 수 있는 경우(즉, 사용자가 써서 사용할 수 있는 디렉터리에 있는 경우) 관리자가 이미 특별히 허용하지 않은 경우 실행을 허용하지 않습니다. 사용자가 맬웨어를 설치하도록 속이는 경우, 사용자가 실행되는 앱의 취약점이 맬웨어 설치를 시도하거나 사용자가 의도적으로 권한이 없는 앱 또는 스크립트를 실행하려고 하면 정책 실행이 중지됩니다.

### <a name="signer-requests"></a>서명자 요청

서명자 요청을 제출하여 신뢰하는 소프트웨어 게시자가 제공하는 앱을 *알려 드립니다.* 이렇게 하면 해당 신뢰 정보를 기준 응용 프로그램 제어 정책에 추가하고 해당 게시자 인증서로 서명된 모든 소프트웨어가 장치에서 실행될 수 있습니다.

## <a name="audit-and-enforced-policies"></a>정책 감사 및 적용

Microsoft Managed Desktop 두 가지 Microsoft Intune 정책을 사용하여 앱 제어를 제공합니다.

### <a name="audit-policy"></a>감사 정책
이 정책은 적용된 정책에 의해 앱 또는 스크립트가 차단될지 여부를 기록하는 로그를 만듭니다. 감사 정책은 앱 제어 규칙을 적용하지 않습니다. 응용 프로그램에 게시자 면제가 필요한지 여부를 식별하기 위한 테스트 목적으로 사용됩니다. 지정된 앱 또는 스크립트의 실행 또는 설치를 차단하는 대신 이벤트 뷰어에 경고(8003 또는 8006 이벤트)를 기록합니다.

### <a name="enforced-policy"></a>적용된 정책
이 정책은 앱 또는 스크립트가 차단될 때마다 트러스터가 실행되지 않는 앱과 스크립트를 차단하고 로그를 만듭니다. 적용된 정책은 표준 사용자가 사용자가 작성 가능한 위치에 저장된 앱 또는 스크립트를 실행하지 못하도록 합니다.

테스트 그룹의 장치에는 응용 프로그램에서 문제를 일으킬 수 있는지 여부를 확인할 수 있도록 감사 정책이 적용됩니다. 다른 모든 그룹(첫 번째, 빠르기 및 광범위)은 적용된 정책을 사용하며, 따라서 해당 그룹의 사용자는 불안정한 앱 또는 스크립트를 실행할 수 없습니다.







