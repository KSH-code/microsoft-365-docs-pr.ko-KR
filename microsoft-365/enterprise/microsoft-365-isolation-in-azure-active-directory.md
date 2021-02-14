---
title: Azure Active Directory의 Microsoft 365 고리 및 액세스 제어
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
description: 이 문서에서는 Azure Active Directory 내에서 격리된 여러 테넌트의 데이터를 격리하기 위해 격리 및 액세스 제어가 작동되는 방법을 설명합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 198e1f37a7378d14d5a4ad28d5bce9d480b2c49e
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332415"
---
# <a name="microsoft-365-isolation-and-access-control-in-azure-active-directory"></a><span data-ttu-id="0b1f1-103">Azure Active Directory의 Microsoft 365 고리 및 액세스 제어</span><span class="sxs-lookup"><span data-stu-id="0b1f1-103">Microsoft 365 Isolation and Access Control in Azure Active Directory</span></span>

<span data-ttu-id="0b1f1-104">Azure AD(Azure Active Directory)는 논리 데이터와의 보안을 유지하여 여러 테넌트가 호스팅될 수 있도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0b1f1-104">Azure Active Directory (Azure AD) was designed to host multiple tenants in a highly secure way through logical data isolation.</span></span> <span data-ttu-id="0b1f1-105">Azure AD에 대한 액세스는 권한 부여 계층에 의해 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b1f1-105">Access to Azure AD is gated by an authorization layer.</span></span> <span data-ttu-id="0b1f1-106">Azure AD는 테넌트 컨테이너를 보안 경계로 사용하는 고객을 격리하여 공동 테넌트가 콘텐츠에 액세스하거나 손상되지 못하게 고객의 콘텐츠를 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="0b1f1-106">Azure AD isolates customers using tenant containers as security boundaries to safeguard a customer's content so that the content cannot be accessed or compromised by co-tenants.</span></span> <span data-ttu-id="0b1f1-107">Azure AD의 권한 부여 계층에 의해 다음 세 가지 확인이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b1f1-107">Three checks are performed by Azure AD's authorization layer:</span></span>

- <span data-ttu-id="0b1f1-108">보안 주체가 Azure AD 테넌트에 액세스할 수 있도록 설정되어 있나요?</span><span class="sxs-lookup"><span data-stu-id="0b1f1-108">Is the principal enabled for access to Azure AD tenant?</span></span>
- <span data-ttu-id="0b1f1-109">보안 주체가 이 테넌트의 데이터에 액세스할 수 있도록 설정되어 있습니까?</span><span class="sxs-lookup"><span data-stu-id="0b1f1-109">Is the principal enabled for access to data in this tenant?</span></span>
- <span data-ttu-id="0b1f1-110">이 테넌트의 보안 주체 역할은 요청된 데이터 액세스 유형에 대해 권한을 부여합니까?</span><span class="sxs-lookup"><span data-stu-id="0b1f1-110">Is the principal's role in this tenant authorized for the type of data access requested?</span></span>

<span data-ttu-id="0b1f1-111">적절한 인증 및 토큰 또는 인증서 없이는 응용 프로그램, 사용자, 서버 또는 서비스가 Azure AD에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0b1f1-111">No application, user, server, or service can access Azure AD without the proper authentication and token or certificate.</span></span> <span data-ttu-id="0b1f1-112">요청에 적절한 자격 증명이 함께 제공되지 않는 경우 요청이 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b1f1-112">Requests are rejected if they are not accompanied by proper credentials.</span></span>

<span data-ttu-id="0b1f1-113">효과적으로 Azure AD는 테넌트가 소유하고 관리하는 컨테이너에 대한 정책 및 사용 권한과 함께 자체 보호된 컨테이너에 각 테넌트가 호스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b1f1-113">Effectively, Azure AD hosts each tenant in its own protected container, with policies and permissions to and within the container solely owned and managed by the tenant.</span></span>
 
![Azure 컨테이너](../media/office-365-isolation-azure-container.png)

<span data-ttu-id="0b1f1-115">테넌트 컨테이너의 개념은 포털에서 영구적 저장소까지 모든 계층의 디렉터리 서비스에 깊이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b1f1-115">The concept of tenant containers is deeply ingrained in the directory service at all layers, from portals all the way to persistent storage.</span></span> <span data-ttu-id="0b1f1-116">여러 Azure AD 테넌트 메타데이터가 동일한 실제 디스크에 저장되는 경우에도 디렉터리 서비스에서 정의한 것 외의 컨테이너 간에 관계가 없습니다. 이는 테넌트 관리자가 받아들입니다.</span><span class="sxs-lookup"><span data-stu-id="0b1f1-116">Even when multiple Azure AD tenant metadata is stored on the same physical disk, there is no relationship between the containers other than what is defined by the directory service, which in turn is dictated by the tenant administrator.</span></span> <span data-ttu-id="0b1f1-117">먼저 권한 부여 계층을 거치지 않고는 요청하는 응용 프로그램 또는 서비스에서 Azure AD 저장소에 직접 연결될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0b1f1-117">There can be no direct connections to Azure AD storage from any requesting application or service without first going through the authorization layer.</span></span>

<span data-ttu-id="0b1f1-118">아래 예제에서 Contoso와 Fabrikam에는 별도의 전용 컨테이너가 있으며, 이러한 컨테이너가 서버 및 저장소와 같은 동일한 기반 인프라 중 일부를 공유할 수 있는 경우에도 서로 분리된 상태로 유지되고 권한 부여 및 액세스 제어 계층에 의해 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b1f1-118">In the example below, Contoso and Fabrikam both have separate, dedicated containers, and even though those containers may share some of the same underlying infrastructure, such as servers and storage, they remain separate and isolated from each other, and gated by layers of authorization and access control.</span></span>
 
![Azure 전용 컨테이너](../media/office-365-isolation-azure-dedicated-containers.png)

<span data-ttu-id="0b1f1-120">또한 Azure AD 내에서 실행할 수 있는 응용 프로그램 구성 요소는 없습니다. 또한 한 테넌트가 다른 테넌트의 무결성을 과도하게 위반하거나, 다른 테넌트의 액세스 암호화 키에 액세스하거나, 서버에서 원시 데이터를 읽을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0b1f1-120">In addition, there are no application components that can execute from within Azure AD, and it is not possible for one tenant to forcibly breach the integrity of another tenant, access encryption keys of another tenant, or read raw data from the server.</span></span>

<span data-ttu-id="0b1f1-121">기본적으로 Azure AD는 다른 테넌트의 ID에 의해 발급된 모든 작업을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0b1f1-121">By default, Azure AD disallows all operations issued by identities in other tenants.</span></span> <span data-ttu-id="0b1f1-122">각 테넌트는 클레임 기반 액세스 제어를 통해 Azure AD 내에서 논리적으로 격리됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b1f1-122">Each tenant is logically isolated within Azure AD through claims-based access controls.</span></span> <span data-ttu-id="0b1f1-123">디렉터리 데이터의 읽기 및 쓰기는 테넌트 컨테이너로 범위가 지정됩니다. 내부 추상화 계층과 RBAC(역할 기반 액세스 제어) 계층을 통해 테넌트를 보안 경계로 함께 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="0b1f1-123">Reads and writes of directory data are scoped to tenant containers, and gated by an internal abstraction layer and a role-based access control (RBAC) layer, which together enforce the tenant as the security boundary.</span></span> <span data-ttu-id="0b1f1-124">모든 디렉터리 데이터 액세스 요청은 이러한 계층에서 처리하며 Microsoft 365의 모든 액세스 요청은 위의 논리에 따라 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b1f1-124">Every directory data access request is processed by these layers and every access request in Microsoft 365 is policed by the logic above.</span></span>

<span data-ttu-id="0b1f1-125">Azure AD에는 북미, 미국 정부, 유럽 연합, 독일 및 World Wide 파티션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b1f1-125">Azure AD has North America, U.S. Government, European Union, Germany, and World Wide partitions.</span></span> <span data-ttu-id="0b1f1-126">테넌트가 단일 파티션에 있으며 파티션에는 여러 테넌트가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b1f1-126">A tenant exists in a single partition, and partitions can contain multiple tenants.</span></span> <span data-ttu-id="0b1f1-127">파티션 정보는 사용자로부터 추상화됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b1f1-127">Partition information is abstracted away from users.</span></span> <span data-ttu-id="0b1f1-128">주어진 파티션(해당 파티션 내의 모든 테넌트 포함)이 여러 데이터 센터로 복제됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b1f1-128">A given partition (including all the tenants within it) is replicated to multiple datacenters.</span></span> <span data-ttu-id="0b1f1-129">테넌트의 파티션은 테넌트의 속성(예: 국가 코드)에 따라 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b1f1-129">The partition for a tenant is chosen based on properties of the tenant (e.g., the country code).</span></span> <span data-ttu-id="0b1f1-130">각 파티션의 비밀 및 기타 중요한 정보는 전용 키로 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b1f1-130">Secrets and other sensitive information in each partition is encrypted with a dedicated key.</span></span> <span data-ttu-id="0b1f1-131">키는 새 파티션을 만들 때 자동으로 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b1f1-131">The keys are generated automatically when a new partition is created.</span></span>

<span data-ttu-id="0b1f1-132">Azure AD 시스템 기능은 각 사용자 세션에 대한 고유한 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="0b1f1-132">Azure AD system functionalities are a unique instance to each user session.</span></span> <span data-ttu-id="0b1f1-133">또한 Azure AD는 암호화 기술을 사용하여 네트워크 수준에서 공유 시스템 리소스를 차단하여 무단 및 의도하지 않은 정보 전송을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="0b1f1-133">In addition, Azure AD uses encryption technologies to provide isolation of shared system resources at the network level to prevent unauthorized and unintended transfer of information.</span></span>
