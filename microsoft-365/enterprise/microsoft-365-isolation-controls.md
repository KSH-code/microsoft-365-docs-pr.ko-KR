---
title: Microsoft 365 격리 제어
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
description: 서비스가 상호 작동하거나 필요한 Microsoft 365 자율적으로 작동할 수 있도록 하여 제어 내에서의 작동 방식에 대해 알아보습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 514b12e44d9e81a18b691ebf3196a3d21157e71b
ms.sourcegitcommit: 27addd4dac07926528b788215d2dcd0e46301eb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2021
ms.locfileid: "53464130"
---
# <a name="microsoft-365-isolation-controls"></a>Microsoft 365 격리 제어 

Microsoft는 Microsoft의 다중 테넌트 아키텍처가 엔터프라이즈 수준의 보안Microsoft 365 기밀성, 개인 정보 보호, 무결성, 로컬, 국제 및 가용성 표준을 지원하도록 지속적으로 [작업합니다.](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons) Microsoft에서 제공하는 서비스의 규모와 범위는 사용자 개입이 많은 서비스를 관리하기 어렵고 Microsoft 365 비가치적입니다. Microsoft 365 서비스는 여러 전역으로 분산된 데이터 센터를 통해 제공되고 각 서비스는 휴먼 터치 또는 고객 콘텐츠에 대한 액세스가 필요한 몇 가지 작업으로 고도로 자동화됩니다. 당사의 직원은 자동화된 도구와 매우 안전한 원격 액세스를 사용하여 이러한 서비스 및 데이터 센터를 지원하고 있습니다. 

Microsoft 365 중요한 비즈니스 기능을 제공하고 전체 비즈니스 환경을 제공하는 여러 Microsoft 365 구성됩니다. 이러한 각 서비스는 자체 포함하며 서로 통합하도록 디자인됩니다.

Microsoft 365 다음 원칙에 따라 디자인됩니다.

 - **[서비스 지향 아키텍처](/previous-versions/aa480021(v=msdn.10)):** 잘 정의된 비즈니스 기능을 제공하는 상호 관리 가능한 서비스 형태로 소프트웨어를 디자인하고 개발합니다.
 - **[Operational Security Assurance:](https://www.microsoft.com/download/details.aspx?id=40872)** [Microsoft](https://www.microsoft.com/sdl/default.aspx)보안 개발 수명 주기, Microsoft 보안 대응 센터, 사이버 보안 위협 [](https://technet.microsoft.com/library/dn440717.aspx)환경의 심층 인식 등 Microsoft 고유의 다양한 기능을 통해 얻은 지식을 통합하는 프레임워크입니다.

Microsoft 365 서비스는 상호 운영되지만 서로 독립적으로 자율 서비스로 배포 및 운영될 수 있도록 설계 및 구현됩니다. Microsoft는 조직의 자산을 무단 또는 Microsoft 365 잘못 수정하거나 오용할 기회를 줄이기 위해 조직에 대한 책임 영역과 의무를 세분화합니다. Microsoft 365 팀은 포괄적인 역할 기반 액세스 제어 메커니즘의 일부로 역할을 정의했습니다.

## <a name="customer-content-isolation"></a>고객 콘텐츠 고리

테넌트의 모든 고객 콘텐츠는 다른 테넌트 및 테넌트 관리에 사용되는 운영 및 시스템 데이터에서 Microsoft 365. 모든 서비스 또는 응용 Microsoft 365 손상 위험을 최소화하기 위해 여러 형태의 보호가 Microsoft 365 구현됩니다. 또한 여러 형태의 보호를 통해 테넌트 또는 테넌트 시스템 자체의 정보에 무단으로 Microsoft 365 방지할 수 있습니다.

Microsoft가 테넌트 데이터 내에서 논리적으로 테넌트 데이터를 Microsoft 365 방법에 대한 자세한 내용은 에서 [테넌트 Microsoft 365.](microsoft-365-tenant-isolation-overview.md)