---
title: Microsoft 365 에지 제어
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
description: 서비스가 상호 작동하거나 필요한 경우 자율적으로 작동할 수 있도록 하는 Microsoft 365 내에서의 고리 컨트롤 작동 방법에 대해 자세히 알아보습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bb0989f19002267ab92bf184a12a4076f753580e
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332379"
---
# <a name="microsoft-365-isolation-controls"></a>Microsoft 365 에지 제어 

Microsoft는 Microsoft 365의 다중 테넌트 아키텍처가 엔터프라이즈 수준의 보안, 기밀성, 개인 정보 보호, 무결성, 로컬, 국제 및 가용성 표준을 지원하도록 지속적으로 [작업하고 있습니다.](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons) Microsoft에서 제공하는 서비스의 규모와 범위를 통해 Microsoft 365를 상당한 사람의 상호 작용으로 관리하기 어렵고 경제적이지 않습니다. Microsoft 365 서비스는 각각 수동 터치 또는 고객 콘텐츠에 대한 액세스가 필요한 몇 가지 작업으로 고도로 자동화된 여러 전역으로 분산된 데이터 센터를 통해 제공됩니다. 직원은 자동화된 도구와 높은 보안 원격 액세스를 사용하여 이러한 서비스 및 데이터 센터를 지원하고 있습니다. 

Microsoft 365는 중요한 비즈니스 기능을 제공하고 전체 Microsoft 365 경험에 기여하는 여러 서비스로 구성됩니다. 이러한 각 서비스는 자체 포함하며 서로 통합하도록 디자인됩니다.

Microsoft 365는 다음 원칙에 따라 설계됩니다.

 - **[서비스 지향 아키텍처:](https://docs.microsoft.com/previous-versions/aa480021(v=msdn.10))** 잘 정의된 비즈니스 기능을 제공하는 상호 연동 가능한 서비스 형태로 소프트웨어를 디자인 및 개발합니다.
 - **[Operational Security Assurance](https://www.microsoft.com/download/details.aspx?id=40872):** Microsoft 보안 개발 수명 주기, Microsoft 보안 대응 센터 [](https://www.microsoft.com/sdl/default.aspx)및 사이버 보안 [](https://technet.microsoft.com/library/dn440717.aspx)위협 환경의 심층 인식을 포함하여 Microsoft 고유의 다양한 기능을 통해 얻은 지식을 통합하는 프레임워크입니다.

Microsoft 365 서비스는 상호 운영되지만 서로 독립적으로 자율 서비스로 배포 및 운영될 수 있도록 설계 및 구현됩니다. Microsoft는 조직의 자산을 무단 또는 의도치 않은 수정 또는 오용할 기회를 줄이기 위해 Microsoft 365에 대한 의무 및 책임 영역을 나란히 합니다. Microsoft 365 팀은 포괄적인 역할 기반 액세스 제어 메커니즘의 일부로 역할을 정의했습니다.

## <a name="customer-content-isolation"></a>고객 콘텐츠 고리

테넌트의 모든 고객 콘텐츠는 Microsoft 365 관리에 사용되는 운영 및 시스템 데이터와 다른 테넌트에서 격리됩니다. Microsoft 365 서비스 또는 응용 프로그램의 손상 위험을 최소화하기 위해 Microsoft 365 전체에서 여러 형태의 보호가 구현됩니다. 또한 여러 형태의 보호를 통해 테넌트 또는 Microsoft 365 시스템 자체의 정보에 무단으로 액세스할 수 없습니다.

Microsoft가 Microsoft 365 내에서 테넌트 데이터의 논리적 고지를 구현하는 방법에 대한 자세한 내용은 [Microsoft 365의](microsoft-365-tenant-isolation-overview.md)테넌트 고지를 참조하세요.
