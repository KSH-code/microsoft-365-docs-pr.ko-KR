---
title: Microsoft 365의 테넌트 고리
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: 이 문서에는 Microsoft가 Microsoft 365와 같은 클라우드 서비스에서 테넌트를 강제로 적용하는 방법에 대한 요약이 포함되어 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c9af522c71f3b089c8f2f198f861bcac8a0011a2
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384940"
---
# <a name="tenant-isolation-in-microsoft-365"></a>Microsoft 365의 테넌트 고리

클라우드 컴퓨팅의 주요 이점 중 하나는 많은 고객에 걸쳐 동시에 공유되는 공유 인프라의 개념으로 확장이 이르기 위한 것입니다. 이 개념을 다중 테넌시라고 *합니다.* Microsoft는 클라우드 서비스의 다중 테넌트 아키텍처가 엔터프라이즈 수준의 보안, 기밀성, 개인 정보 보호, 무결성 및 가용성 표준을 지원하도록 지속적으로 작업하고 있습니다.

[신뢰할](https://www.microsoft.com/trust-center) 수 있는 컴퓨팅 및 보안 개발 수명 주기에서 [](https://www.microsoft.com/securityengineering/sdl/)수집된 상당한 투자 및 경험에 따라 Microsoft 클라우드 서비스는 모든 테넌트가 다른 모든 테넌트에 잠재적으로 적극적일 수 있는 것으로 가정하여 디자인된 것이고, 한 테넌트의 작업이 다른 테넌트의 보안 또는 서비스에 영향을 주지 않도록 방지하거나 다른 테넌트의 콘텐츠에 액세스하지 못하도록 보안 조치를 구현했습니다.

다중 테넌트 환경에서 테넌트의 두 가지 주요 목표는 다음입니다.

1.    테넌트 전체의 고객 콘텐츠 유출 또는 무단 액세스 방지 및
2.    한 테넌트의 작업이 다른 테넌트의 서비스에 부정적인 영향을 주지 않도록 방지

고객이 Microsoft 365 서비스 또는 응용 프로그램을 타협하거나 다른 테넌트 또는 Microsoft 365 시스템 자체의 정보에 무단으로 액세스하지 못하게 방지하기 위해 Microsoft 365 전체에 다양한 형태의 보호가 구현되었습니다.

- Microsoft 365 서비스에 대한 각 테넌트 내의 고객 콘텐츠에 대한 논리적 고지는 Azure Active Directory 권한 부여 및 역할 기반 액세스 제어를 통해 달성됩니다.
- SharePoint Online은 저장소 수준에서 데이터 고리 메커니즘을 제공합니다.
- Microsoft는 엄격한 물리적 보안, 백그라운드 심사 및 다계층 암호화 전략을 사용하여 고객 콘텐츠의 기밀성 및 무결성을 보호합니다. 모든 Microsoft 365 데이터 센터에는 생체 인식 액세스 제어가 있습니다. 이 경우 물리적 액세스를 얻기 위해 대부분 팜 인쇄가 요구됩니다. 또한 모든 미국 기반 Microsoft 직원은 채용 프로세스의 일부로 표준 배경 검사를 완료해야 합니다. Microsoft 365의 관리 액세스에 사용되는 컨트롤에 대한 자세한 내용은 [Microsoft 365 관리 액세스 제어를 참조하세요.](microsoft-365-administrative-access-controls-overview.md)
- Microsoft 365는 BitLocker, 파일당 암호화, TLS(전송 계층 보안) 및 IPsec(인터넷 프로토콜 보안)을 포함하여 미사용 및 전송 중 고객 콘텐츠를 암호화하는 서비스 쪽 기술을 사용합니다. Microsoft 365의 암호화에 대한 자세한 내용은 [Microsoft 365의](../compliance/office-365-encryption-in-the-microsoft-cloud-overview.md)데이터 암호화 기술을 참조하세요.

위에 나열된 보호는 물리적으로만 제공된 위협 방지 및 완화 기능을 제공하는 강력한 논리적 차단 컨트롤을 제공합니다.

## <a name="related-links"></a>관련 링크

- [Azure Active Directory에서 격리 및 액세스 제어](microsoft-365-isolation-in-azure-active-directory.md)
- [Office Graph 및 Delve에서 테넌트 격리](microsoft-365-isolation-in-graph-and-delve.md)
- [Microsoft 365 검색에서 테넌트 격리](microsoft-365-isolation-in-microsoft-365-search.md)
- [Office 365 비디오에서 테넌트 격리](microsoft-365-isolation-in-microsoft-365-video.md)
- [리소스 제한 사항](microsoft-365-resource-limits.md)
- [테넌트 경계 모니터링 및 테스트](microsoft-365-monitoring-and-testing.md)
- [Microsoft 365에서 격리 및 액세스 제어](microsoft-365-isolation-in-microsoft-365.md)
