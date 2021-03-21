---
title: Microsoft 365 고리원화 컨트롤
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
description: 서비스가 상호 작동하거나 필요한 경우 자율적으로 작동할 수 있도록 하는 Microsoft 365 내에서의 고리 제어가 작동하는 방법을 알아보습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 514b12e44d9e81a18b691ebf3196a3d21157e71b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918945"
---
# <a name="microsoft-365-isolation-controls"></a><span data-ttu-id="86307-103">Microsoft 365 고리원화 컨트롤</span><span class="sxs-lookup"><span data-stu-id="86307-103">Microsoft 365 isolation controls</span></span> 

<span data-ttu-id="86307-104">Microsoft는 Microsoft 365의 다중 테넌트 아키텍처가 엔터프라이즈 수준의 보안, 기밀성, 개인 정보 보호, 무결성, 로컬, 국제 및 가용성 표준을 지원하도록 지속적으로 [작업합니다.](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons)</span><span class="sxs-lookup"><span data-stu-id="86307-104">Microsoft continuously works to ensure that the multi-tenant architecture of Microsoft 365 supports enterprise-level security, confidentiality, privacy, integrity, local, international, and availability [standards](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons).</span></span> <span data-ttu-id="86307-105">Microsoft에서 제공하는 서비스의 규모와 범위는 사람의 상당한 상호 작용을 통해 Microsoft 365를 관리하기 어렵고 경제적이지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="86307-105">The scale and the scope of services provided by Microsoft make it difficult and non-economical to manage Microsoft 365 with significant human interaction.</span></span> <span data-ttu-id="86307-106">Microsoft 365 서비스는 여러 전역으로 분산된 데이터 센터를 통해 제공됩니다. 각 서비스는 휴먼 터치 또는 고객 콘텐츠에 대한 액세스가 필요한 몇 가지 작업으로 매우 자동화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86307-106">Microsoft 365 services are provided through multiple globally distributed data centers, each highly automated with few operations requiring a human touch or any access to customer content.</span></span> <span data-ttu-id="86307-107">당사의 직원은 자동화된 도구와 매우 안전한 원격 액세스를 사용하여 이러한 서비스 및 데이터 센터를 지원하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86307-107">Our staff supports these services and data centers using automated tools and highly secure remote access.</span></span> 

<span data-ttu-id="86307-108">Microsoft 365는 중요한 비즈니스 기능을 제공하고 전체 Microsoft 365 경험에 기여하는 여러 서비스로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="86307-108">Microsoft 365 is composed of multiple services that provide important business functionality and contribute to the entire Microsoft 365 experience.</span></span> <span data-ttu-id="86307-109">이러한 각 서비스는 자체 포함하며 서로 통합하도록 디자인됩니다.</span><span class="sxs-lookup"><span data-stu-id="86307-109">Each of these services is self-contained and designed to integrate with one another.</span></span>

<span data-ttu-id="86307-110">Microsoft 365는 다음 원칙에 따라 설계됩니다.</span><span class="sxs-lookup"><span data-stu-id="86307-110">Microsoft 365 is designed with the following principles:</span></span>

 - <span data-ttu-id="86307-111">**[서비스 지향 아키텍처](/previous-versions/aa480021(v=msdn.10)):** 잘 정의된 비즈니스 기능을 제공하는 상호 관리 가능한 서비스 형태로 소프트웨어를 디자인하고 개발합니다.</span><span class="sxs-lookup"><span data-stu-id="86307-111">**[Service-Oriented Architecture](/previous-versions/aa480021(v=msdn.10)):** designing and developing software in the form of interoperable services providing well-defined business functionality.</span></span>
 - <span data-ttu-id="86307-112">**[Operational Security Assurance:](https://www.microsoft.com/download/details.aspx?id=40872)** [Microsoft](https://www.microsoft.com/sdl/default.aspx)보안 개발 수명 주기, Microsoft 보안 대응 센터, 사이버 보안 위협 [](https://technet.microsoft.com/library/dn440717.aspx)환경의 심층 인식 등 Microsoft 고유의 다양한 기능을 통해 얻은 지식을 통합하는 프레임워크입니다.</span><span class="sxs-lookup"><span data-stu-id="86307-112">**[Operational Security Assurance](https://www.microsoft.com/download/details.aspx?id=40872):** a framework that incorporates the knowledge gained through various capabilities that are unique to Microsoft, including the Microsoft [Security Development Lifecycle](https://www.microsoft.com/sdl/default.aspx), the [Microsoft Security Response Center](https://technet.microsoft.com/library/dn440717.aspx), and deep awareness of the cybersecurity threat landscape.</span></span>

<span data-ttu-id="86307-113">Microsoft 365 서비스는 상호 운영되지만 서로 독립적으로 자율 서비스로 배포 및 운영될 수 있도록 설계 및 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="86307-113">Microsoft 365 services inter-operate with each other, but are designed and implemented so they can be deployed and operated as autonomous services, independent of each other.</span></span> <span data-ttu-id="86307-114">Microsoft는 조직의 자산을 무단 또는 의도치 않은 수정 또는 오용할 기회를 줄이기 위해 Microsoft 365에 대한 의무와 책임 영역을 나란히 합니다.</span><span class="sxs-lookup"><span data-stu-id="86307-114">Microsoft segregates duties and areas of responsibility for Microsoft 365 to reduce opportunities for unauthorized or unintentional modification or misuse of the organization's assets.</span></span> <span data-ttu-id="86307-115">Microsoft 365 팀은 포괄적인 역할 기반 액세스 제어 메커니즘의 일부로 역할을 정의했습니다.</span><span class="sxs-lookup"><span data-stu-id="86307-115">Microsoft 365 teams have defined roles as part of a comprehensive role-based access control mechanism.</span></span>

## <a name="customer-content-isolation"></a><span data-ttu-id="86307-116">고객 콘텐츠 고리</span><span class="sxs-lookup"><span data-stu-id="86307-116">Customer content isolation</span></span>

<span data-ttu-id="86307-117">테넌트의 모든 고객 콘텐츠는 다른 테넌트와 Microsoft 365 관리에 사용되는 운영 및 시스템 데이터에서 격리됩니다.</span><span class="sxs-lookup"><span data-stu-id="86307-117">All customer content in a tenant is isolated from other tenants and from operations and systems data used in the management of Microsoft 365.</span></span> <span data-ttu-id="86307-118">Microsoft 365 서비스 또는 응용 프로그램의 손상 위험을 최소화하기 위해 Microsoft 365 전체에서 여러 형태의 보호가 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="86307-118">Multiple forms of protection are implemented throughout Microsoft 365 to minimize the risk of compromise of any Microsoft 365 service or application.</span></span> <span data-ttu-id="86307-119">또한 여러 형태의 보호를 통해 테넌트 또는 Microsoft 365 시스템 자체의 정보에 무단으로 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="86307-119">Multiple forms of protection also prevent unauthorized access to the information of tenants or the Microsoft 365 system itself.</span></span>

<span data-ttu-id="86307-120">Microsoft가 Microsoft 365 내에서 테넌트 데이터의 논리적 고지를 구현하는 방법에 대한 자세한 내용은 [Microsoft 365에서 테넌트 Isolation을 참조하세요.](microsoft-365-tenant-isolation-overview.md)</span><span class="sxs-lookup"><span data-stu-id="86307-120">For information about how Microsoft implements logical isolation of tenant data within Microsoft 365, see [Tenant Isolation in Microsoft 365](microsoft-365-tenant-isolation-overview.md).</span></span>