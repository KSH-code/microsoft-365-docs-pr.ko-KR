---
title: Microsoft 클라우드 제품용 구독, 라이선스, 계정 및 테넌트
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365initiative-coredeploy
f1.keywords:
- CSH
ms.assetid: c720cffc-f9b5-4f43-9100-422f86a1027c
ms.custom:
- seo-marvel-apr2020
- Ent_Architecture
description: Microsoft의 클라우드 제품에서 조직, 구독, 라이선스, 사용자 계정 및 테넌트의 관계를 이해합니다.
ms.openlocfilehash: eaf1c2399b5d44ea8d6000042b3258d0e8b5a7de
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909517"
---
# <a name="subscriptions-licenses-accounts-and-tenants-for-microsofts-cloud-offerings"></a><span data-ttu-id="b0e8f-103">Microsoft 클라우드 제품용 구독, 라이선스, 계정 및 테넌트</span><span class="sxs-lookup"><span data-stu-id="b0e8f-103">Subscriptions, licenses, accounts, and tenants for Microsoft's cloud offerings</span></span>

<span data-ttu-id="b0e8f-104">Microsoft는 해당 클라우드 제품 간에 일관된 ID 사용 및 요금 청구를 위해 조직, 구독, 라이선스 및 사용자 계정을 포함하는 계층 구조를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-104">Microsoft provides a hierarchy of organizations, subscriptions, licenses, and user accounts for consistent use of identities and billing across its cloud offerings:</span></span>
  
- <span data-ttu-id="b0e8f-105">Microsoft 365 및 Microsoft Office 365</span><span class="sxs-lookup"><span data-stu-id="b0e8f-105">Microsoft 365 and Microsoft Office 365</span></span>
- <span data-ttu-id="b0e8f-106">Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="b0e8f-106">Microsoft Azure</span></span>
- <span data-ttu-id="b0e8f-107">Microsoft Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="b0e8f-107">Microsoft Dynamics 365</span></span>

## <a name="elements-of-the-hierarchy"></a><span data-ttu-id="b0e8f-108">계층 구조의 요소</span><span class="sxs-lookup"><span data-stu-id="b0e8f-108">Elements of the hierarchy</span></span>

<span data-ttu-id="b0e8f-109">다음은 계층 구조의 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-109">Here are the elements of the hierarchy:</span></span>
  
### <a name="organization"></a><span data-ttu-id="b0e8f-110">조직</span><span class="sxs-lookup"><span data-stu-id="b0e8f-110">Organization</span></span>

<span data-ttu-id="b0e8f-p101">조직은 Microsoft 클라우드 서비스를 사용하는 비즈니스 엔터티를 나타내며, 일반적으로 하나 이상의 공용 DNS(Domain Name System) 도메인 이름(예: contoso.com)으로 식별됩니다. 조직은 구독을 위한 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-p101">An organization represents a business entity that is using Microsoft cloud offerings, typically identified by one or more public Domain Name System (DNS) domain names, such as contoso.com. The organization is a container for subscriptions.</span></span>
  
### <a name="subscriptions"></a><span data-ttu-id="b0e8f-113">구독</span><span class="sxs-lookup"><span data-stu-id="b0e8f-113">Subscriptions</span></span>

<span data-ttu-id="b0e8f-114">구독은 하나 혹은 이상의 Microsoft 클라우드 플랫폼 또는 서비스를 사용하기 위한 Microsoft와의 약정이며 사용자 단위 라이선스 요금이나 클라우드 기반 리소스 소비량을 기준으로 요금이 부과됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-114">A subscription is an agreement with Microsoft to use one or more Microsoft cloud platforms or services, for which charges accrue based on either a per-user license fee or on cloud-based resource consumption.</span></span> 

- <span data-ttu-id="b0e8f-115">Microsoft의 서비스로서의 소프트웨어 (SaaS) 기반 클라우드 서비스(Microsoft 365 및 Dynamics 365)는 사용자 단위 라이선스 요금을 부과합니다.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-115">Microsoft's Software as a Service (SaaS)-based cloud offerings (Microsoft 365 and Dynamics 365) charge per-user license fees.</span></span> 
- <span data-ttu-id="b0e8f-116">Microsoft의 서비스로서의 플랫폼 (PaaS) 및 서비스로서의 인프라 (IaaS) 클라우드 서비스는 (Azure) 클라우드 리소스 소비량을 기반으로 요금을 부과합니다.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-116">Microsoft's Platform as a Service (PaaS) and Infrastructure as a Service (IaaS) cloud offerings (Azure) charge based on cloud resource consumption.</span></span>
 
<span data-ttu-id="b0e8f-p102">평가판 구독을 사용할 수도 있지만, 일정 기간이 지나거나 이용 요금이 다 사용된 후에는 구독이 만료됩니다. 평가판 구독을 유료 구독으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-p102">You can also use a trial subscription, but the subscription expires after a specific amount of time or consumption charges. You can convert a trial subscription to a paid subscription.</span></span>
  
<span data-ttu-id="b0e8f-119">조직은 다수의 Microsoft의 클라우드 서비스를 구독할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-119">Organizations can have multiple subscriptions for Microsoft's cloud offerings.</span></span> <span data-ttu-id="b0e8f-120">그림 1에서는 여러 개의 Microsoft 365 구독, Dynamics 365 구독 및 여러 개의 Azure 구독이 있는 단일 조직을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-120">Figure 1 shows a single organization that has multiple Microsoft 365 subscriptions, a Dynamics 365 subscription, and multiple Azure subscriptions.</span></span>

<span data-ttu-id="b0e8f-121">**그림 1: 여러 개의 조직용 구독 예**</span><span class="sxs-lookup"><span data-stu-id="b0e8f-121">**Figure 1: Example of multiple subscriptions for an organization**</span></span>

![Microsoft의 클라우드 서비스용 구독이 여러 개 있는 예제 조직입니다.](../media/Subscriptions/Subscriptions-Fig1.png)
  
### <a name="licenses"></a><span data-ttu-id="b0e8f-123">라이선스</span><span class="sxs-lookup"><span data-stu-id="b0e8f-123">Licenses</span></span>

<span data-ttu-id="b0e8f-124">Microsoft의 SaaS 클라우드 제품의 경우 라이선스를 통해 특정 사용자 계정이 클라우드 서비스를 사용할 수 있도록 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-124">For Microsoft's SaaS cloud offerings, a license allows a specific user account to use the services of the cloud offering.</span></span> <span data-ttu-id="b0e8f-125">구독의 일부로서 구독자에게 고정 월별 요금이 청구됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-125">You are charged a fixed monthly fee as part of your subscription.</span></span> <span data-ttu-id="b0e8f-126">관리자는 구독의 개별 사용자 계정에 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-126">Administrators assign licenses to individual user accounts in the subscription.</span></span> <span data-ttu-id="b0e8f-127">예를 들어, 그림 2에서 Contoso Corporation는 Microsoft 365 E5를 구독하고 100개의 라이선스를 보유하고 있어 최대 100개의 개별 사용자 계정을 사용하여 Microsoft 365 E5의 기능 및 서비스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-127">For the example in Figure 2, the Contoso Corporation has a Microsoft 365 E5 subscription with 100 licenses, which allows to up to 100 individual user accounts to use Microsoft 365 E5 features and services.</span></span>
  
<span data-ttu-id="b0e8f-128">**그림 2: 조직을 위한 SaaS 기반 구독에 포함된 라이선스**</span><span class="sxs-lookup"><span data-stu-id="b0e8f-128">**Figure 2: Licenses within the SaaS-based subscriptions for an organization**</span></span>

![Microsoft의 SaaS 기반 클라우드 서비스용 구독에 포함된 여러 라이선스 예제입니다.](../media/Subscriptions/Subscriptions-Fig2.png)

>[!Note]
><span data-ttu-id="b0e8f-130">보안 모범 사례에서는 관리 기능에 대한 특정 역할이 할당된 별도의 사용자 계정을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-130">A security best practice is to use separate user accounts that are assigned specific roles for administrative functions.</span></span> <span data-ttu-id="b0e8f-131">이러한 전용 관리자 계정에는 관리되는 클라우드 서비스에 대한 라이선스가 할당될 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-131">These dedicated administrator accounts do not need to be assigned a license for the cloud services that they administer.</span></span> <span data-ttu-id="b0e8f-132">예를 들어 SharePoint 관리자 계정에 Microsoft 365 라이선스를 할당할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-132">For example, a SharePoint administrator account does not need to be assigned a Microsoft 365 license.</span></span>
>

<span data-ttu-id="b0e8f-133">Azure PaaS 기반 클라우드 서비스의 경우 소프트웨어 라이선스가 서비스 가격에 기본적으로 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-133">For Azure PaaS-based cloud services, software licenses are built into the service pricing.</span></span>
  
<span data-ttu-id="b0e8f-p106">Azure IaaS 기반 가상 머신의 경우 가상 머신 이미지에 설치되어 있는 소프트웨어 또는 이미지를 사용하기 위한 추가 라이선스가 필요할 수도 있습니다. 일부 가상 머신 이미지는 설치된 소프트웨어의 라이선스 버전을 가지며 서버에 대한 분당 요금에 해당 요금이 포함됩니다. 제공된 예제는 SQL Server 2014 및 SQL Server 2016에 대한 가상 머신 이미지입니다.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-p106">For Azure IaaS-based virtual machines, additional licenses to use the software or application installed on a virtual machine image might be required. Some virtual machine images have licensed versions of software installed and the cost is included in the per-minute rate for the server. Examples are the virtual machine images for SQL Server 2014 and SQL Server 2016.</span></span> 
  
<span data-ttu-id="b0e8f-p107">일부 가상 머신 이미지에는 평가판 버전의 응용 프로그램이 설치되어 있고 평가 기간 이후에도 사용하려면 추가 소프트웨어 응용 프로그램 라이선스가 필요합니다. 예를 들어, SharePoint Server 2016 평가판 가상 머신 이미지에는 사전 설치된 SharePoint Server 2016 평가판이 포함되어 있습니다. 평가판 만료일 이후에도 SharePoint Server 2016을 계속 사용하려면 Microsoft에서 SharePoint Server 2016 라이선스 및 클라이언트 라이선스를 구입해야 합니다. 이러한 청구 금액은 Azure 구독과는 별개이며, 가상 머신을 실행하는 분당 요금은 여전히 부과됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-p107">Some virtual machine images have trial versions of applications installed and need additional software application licenses for use beyond the trial period. For example, the SharePoint Server 2016 Trial virtual machine image includes a trial version of SharePoint Server 2016 pre-installed. To continue using SharePoint Server 2016 after the trial expiration date, you must purchase a SharePoint Server 2016 license and client licenses from Microsoft. These charges are separate from the Azure subscription and the per-minute rate to run the virtual machine still applies.</span></span>
  
### <a name="user-accounts"></a><span data-ttu-id="b0e8f-141">사용자 계정</span><span class="sxs-lookup"><span data-stu-id="b0e8f-141">User accounts</span></span>

<span data-ttu-id="b0e8f-142">모든 Microsoft 클라우드 서비스의 사용자 계정은 사용자 계정 및 그룹이 포함되어 있는 Azure AD (Azure 액티브 디렉터리) 테넌트에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-142">User accounts for all of Microsoft's cloud offerings are stored in an Azure Active Directory (Azure AD) tenant, which contains user accounts and groups.</span></span> <span data-ttu-id="b0e8f-143">Azure AD 테넌트는 Windows server 기반의 서비스인 Azure AD Connect를 사용하여 기존의 AD DS (액티브 디렉터리 도메인 서비스) 계정과 동기화될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-143">An Azure AD tenant can be synchronized with your existing Active Directory Domain Services (AD DS) accounts using Azure AD Connect, a Windows server-based service.</span></span> <span data-ttu-id="b0e8f-144">이를 디렉터리 동기화라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-144">This is known as directory synchronization.</span></span>
  
<span data-ttu-id="b0e8f-145">그림 3은 조직 계정이 포함된 일반적인 Azure 테넌트를 사용하는 조직의 여러 구독 예를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-145">Figure 3 shows an example of multiple subscriptions of an organization using a common Azure AD tenant that contains the organization's accounts.</span></span>
  
<span data-ttu-id="b0e8f-146">**그림 3: 동일한 Azure 테넌트를 사용하는 조직의 여러 구독**</span><span class="sxs-lookup"><span data-stu-id="b0e8f-146">**Figure 3: Multiple subscriptions of an organization that use the same Azure AD tenant**</span></span>

![모두 동일한 Azure 테넌트를 사용하는 여러 개의 구독이 있는 예제 조직입니다.](../media/Subscriptions/Subscriptions-Fig3.png)
  
### <a name="tenants"></a><span data-ttu-id="b0e8f-148">테넌트</span><span class="sxs-lookup"><span data-stu-id="b0e8f-148">Tenants</span></span>

<span data-ttu-id="b0e8f-149">SaaS 클라우드 제공품의 경우 테넌트는 클라우드 서비스를 제공하는 서버가 있는 지역 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-149">For SaaS cloud offerings, the tenant is the regional location that houses the servers providing cloud services.</span></span> <span data-ttu-id="b0e8f-150">예를 들어, Contoso Corporation은 유럽 지역을 선택하여 파리 본사에 있는 15,000명의 작업자를 위해 Microsoft 365, EMS 및 Dynamics 365 테넌트를 호스트했습니다.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-150">For example, the Contoso Corporation chose the European region to host its Microsoft 365, EMS, and Dynamics 365 tenants for the 15,000 workers in their Paris headquarters.</span></span>
  
<span data-ttu-id="b0e8f-p110">Azure IaaS에 호스트된 Azure PaaS 서비스 및 가상 머신 기반 워크로드는 전 세계의 모든 Azure 데이터 센터에서 테넌시를 둘 수 있습니다. Azure PaaS 앱 또는 서비스를 만들 때는 위치로 사용되고, IaaS 워크로드의 요소로도 알려진 Azure 데이터 센터를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-p110">Azure PaaS services and virtual machine-based workloads hosted in Azure IaaS can have tenancy in any Azure datacenter across the world. You specify the Azure datacenter, known as the location, when you create the Azure PaaS app or service or element of an IaaS workload.</span></span>
  
<span data-ttu-id="b0e8f-153">Azure AD 테넌트는 계정 및 그룹을 포함하는 Azure AD의 특정 인스턴스를 말합니다.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-153">An Azure AD tenant is a specific instance of Azure AD containing accounts and groups.</span></span> <span data-ttu-id="b0e8f-154">Microsoft 365 또는 Dynamics 365의 유료 또는 평가판 구독에는 무료 Azure AD 테넌트가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-154">Paid or trial subscriptions of Microsoft 365 or Dynamics 365 include a free Azure AD tenant.</span></span> <span data-ttu-id="b0e8f-155">Azure AD 테넌트는 다른 Azure 서비스를 포함하지 않으며 Azure 평가판 또는 유료 구독과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-155">This Azure AD tenant does not include other Azure services and is not the same as an Azure trial or paid subscription.</span></span>
  
### <a name="summary-of-the-hierarchy"></a><span data-ttu-id="b0e8f-156">계층 구조의 요약</span><span class="sxs-lookup"><span data-stu-id="b0e8f-156">Summary of the hierarchy</span></span>

<span data-ttu-id="b0e8f-157">간단한 설명은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-157">Here is a quick recap:</span></span>
  
- <span data-ttu-id="b0e8f-158">하나의 조직에 구독이 여러 개일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-158">An organization can have multiple subscriptions</span></span>
    
  - <span data-ttu-id="b0e8f-159">하나의 구독에 라이선스가 여러 개 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-159">A subscription can have multiple licenses</span></span>
    
  - <span data-ttu-id="b0e8f-160">라이선스를 개별 사용자 계정에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-160">Licenses can be assigned to individual user accounts</span></span>
    
  - <span data-ttu-id="b0e8f-161">사용자 계정은 Azure AD테넌트에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-161">User accounts are stored in an Azure AD tenant</span></span>
    
<span data-ttu-id="b0e8f-162">조직, 구독, 라이선스 및 사용자 계정의 관계를 보여주는 예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-162">Here is an example of the relationship of organizations, subscriptions, licenses, and user accounts:</span></span>
  
- <span data-ttu-id="b0e8f-163">공용 도메인 이름으로 식별되는 조직</span><span class="sxs-lookup"><span data-stu-id="b0e8f-163">An organization identified by its public domain name.</span></span>
    
  - <span data-ttu-id="b0e8f-164">사용자 라이선스가 있는 Microsoft 365 E3 구독</span><span class="sxs-lookup"><span data-stu-id="b0e8f-164">A Microsoft 365 E3 subscription with user licenses.</span></span>
    
    <span data-ttu-id="b0e8f-165">사용자 라이선스가 있는 Microsoft 365 E5 구독</span><span class="sxs-lookup"><span data-stu-id="b0e8f-165">A Microsoft 365 E5 subscription with user licenses.</span></span>
    
    <span data-ttu-id="b0e8f-166">사용자 라이선스가 있는 Dynamics 365 구독</span><span class="sxs-lookup"><span data-stu-id="b0e8f-166">A Dynamics 365 subscription with user licenses.</span></span>
    
    <span data-ttu-id="b0e8f-167">여러 Azure 구독</span><span class="sxs-lookup"><span data-stu-id="b0e8f-167">Multiple Azure subscriptions.</span></span>
    
  - <span data-ttu-id="b0e8f-168">일반적인 Azure AD 테넌트에 있는 조직의 사용자 계정</span><span class="sxs-lookup"><span data-stu-id="b0e8f-168">The organization's user accounts in a common Azure AD tenant.</span></span>
    
<span data-ttu-id="b0e8f-169">다수의 Microsoft 클라우드 서비스의 구독은 공통 ID제공자 역할을 하는 동일한 Azure AD 테넌트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-169">Multiple Microsoft cloud offering subscriptions can use the same Azure AD tenant that acts as a common identity provider.</span></span> <span data-ttu-id="b0e8f-170">온-프레미스 AD DS의 동기화된 계정을 포함하는 중앙 Azure AD 테넌트는 조직에 클라우드 기반의 서비스로서의 ID (IDaaS)를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-170">A central Azure AD tenant that contains the synchronized accounts of your on-premises AD DS provides cloud-based Identity as a Service (IDaaS) for your organization.</span></span> 
  
<span data-ttu-id="b0e8f-171">**그림 4: 조직에 대한 동기화된 온-프레미스 계정 및 IDaaS**</span><span class="sxs-lookup"><span data-stu-id="b0e8f-171">**Figure 4: Synchronized on-premises accounts and IDaaS for an organization**</span></span>

![조직에 대한 IDaaS(Identity as a Service)입니다.](../media/Subscriptions/Subscriptions-Fig4.png)
  
<span data-ttu-id="b0e8f-p113">그림 4는 일반적인 Azure AD 테넌트가 Azure AD Domains Services를 사용하는 Microsoft의 SaaS 클라우드 서비스, Azure PaaS 앱 및 Azure IaaS의 가상 머신에서 사용되는 방법을 보여 줍니다. Azure AD Connect는 온-프레미스 AD DS(Active Directory Domain Services) 포리스트를 Azure AD 테넌트와 동기화합니다.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-p113">Figure 4 shows how a common Azure AD tenant is used by Microsoft's SaaS cloud offerings, Azure PaaS apps, and virtual machines in Azure IaaS that use Azure AD Domain Services. Azure AD Connect synchronizes the on-premises AD DS forest with the Azure AD tenant.</span></span>
  
## <a name="combining-subscriptions-for-multiple-microsoft-cloud-offerings"></a><span data-ttu-id="b0e8f-175">여러 Microsoft 클라우드 서비스에 대한 구독 결합</span><span class="sxs-lookup"><span data-stu-id="b0e8f-175">Combining subscriptions for multiple Microsoft cloud offerings</span></span>

<span data-ttu-id="b0e8f-176">다음 표에서는 한 가지 유형의 클라우드 서비스에 대한 구독이 이미 있고(첫 번째 열 아래쪽에 레이블 참조), 다른 클라우드 서비스에 대한 구독을 추가하는 경우(열 가로 방향으로) 여러 Microsoft 클라우드 서비스를 결합하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-176">The following table describes how you can combine multiple Microsoft cloud offerings based on already having a subscription for one type of cloud offering (the labels going down the first column) and adding a subscription for a different cloud offering (going across the columns).</span></span>
  
||<span data-ttu-id="b0e8f-177">**Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="b0e8f-177">**Microsoft 365**</span></span>|<span data-ttu-id="b0e8f-178">**Azure**</span><span class="sxs-lookup"><span data-stu-id="b0e8f-178">**Azure**</span></span>|<span data-ttu-id="b0e8f-179">**Dynamics 365**</span><span class="sxs-lookup"><span data-stu-id="b0e8f-179">**Dynamics 365**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b0e8f-180">**Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="b0e8f-180">**Microsoft 365**</span></span> <br/> |<span data-ttu-id="b0e8f-181">해당 없음</span><span class="sxs-lookup"><span data-stu-id="b0e8f-181">NA</span></span>  <br/> |<span data-ttu-id="b0e8f-182">Azure Portal에서 조직에 Azure 구독을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-182">You add an Azure subscription to your organization from the Azure portal.</span></span>  <br/> |<span data-ttu-id="b0e8f-183">Microsoft 365 관리 센터에서 조직에 Dynamics 365 구독을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-183">You add a Dynamics 365 subscription to your organization from the Microsoft 365 admin center.</span></span>  <br/> |
|<span data-ttu-id="b0e8f-184">**Azure**</span><span class="sxs-lookup"><span data-stu-id="b0e8f-184">**Azure**</span></span> <br/> |<span data-ttu-id="b0e8f-185">조직에 Microsoft 365 구독을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-185">You add a Microsoft 365 subscription to your organization.</span></span>  <br/> |<span data-ttu-id="b0e8f-186">해당 없음</span><span class="sxs-lookup"><span data-stu-id="b0e8f-186">NA</span></span>  <br/> |<span data-ttu-id="b0e8f-187">조직에 Dynamics 365 구독을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-187">You add a Dynamics 365 subscription to your organization.</span></span>  <br/> |
|<span data-ttu-id="b0e8f-188">**Dynamics 365**</span><span class="sxs-lookup"><span data-stu-id="b0e8f-188">**Dynamics 365**</span></span> <br/> |<span data-ttu-id="b0e8f-189">조직에 Microsoft 365 구독을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-189">You add a Microsoft 365 subscription to your organization.</span></span>  <br/> |<span data-ttu-id="b0e8f-190">Azure Portal에서 조직에 Azure 구독을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-190">You add an Azure subscription to your organization from the Azure portal.</span></span>  <br/> |<span data-ttu-id="b0e8f-191">해당 없음</span><span class="sxs-lookup"><span data-stu-id="b0e8f-191">NA</span></span>  <br/> |
   
<span data-ttu-id="b0e8f-192">관리 센터를 사용하면 Microsoft SaaS 기반 서비스를 위해 조직에 구독을 쉽게 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-192">An easy way to add subscriptions to your organization for Microsoft SaaS-based services is through the admin center:</span></span>
  
1. <span data-ttu-id="b0e8f-193">글로벌 관리자 계정을 사용하여 Microsoft 365 관리 센터([https://admin.microsoft.com](https://admin.microsoft.com))에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-193">Sign in to the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) with your global administrator account.</span></span>
    
2. <span data-ttu-id="b0e8f-194">**관리 센터** 홈페이지의 왼쪽 탐색 창에서 **청구** 를 클릭하고 **서비스 구매** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-194">From the left navigation of the **Admin center** home page, click **Billing**, and then **Purchase services**.</span></span>
    
3. <span data-ttu-id="b0e8f-195">**서비스 구매** 페이지에서 새 구독을 구입합니다.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-195">On the **Purchase services** page, purchase your new subscriptions.</span></span>
    
<span data-ttu-id="b0e8f-196">관리 센터는 SaaS 기반 클라우드 서비스에 대한 새 구독에 Microsoft 365 구독의 조직 및 Azure 테넌트를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-196">The admin center assigns the organization and Azure AD tenant of your Microsoft 365 subscription to the new subscriptions for SaaS-based cloud offerings.</span></span>
  
<span data-ttu-id="b0e8f-197">Microsoft 365 구독과 동일한 조직 및 Azure 테넌트를 갖는 Azure 구독을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="b0e8f-197">To add an Azure subscription with the same organization and Azure AD tenant as your Microsoft 365 subscription:</span></span>
  
1. <span data-ttu-id="b0e8f-198">Microsoft 365 전역 관리자 계정을 사용하여 Azure Portal 포털([https://portal.azure.com](https://portal.azure.com))에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-198">Sign in to the Azure portal ([https://portal.azure.com](https://portal.azure.com)) with your Microsoft 365 global administrator account.</span></span>
    
2. <span data-ttu-id="b0e8f-199">왼쪽 탐색 모음에서 **구독** 을 클릭하고 **추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-199">In the left navigation, click **Subscriptions**, and then click **Add**.</span></span>
    
3. <span data-ttu-id="b0e8f-200">**구독 추가** 페이지에서 서비스를 선택하고 결제 정보 및 계약을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-200">On the **Add subscription** page, select an offer and complete the payment information and agreement.</span></span>
    
<span data-ttu-id="b0e8f-201">Azure 및 Microsoft 365 구독으로 따로 구입했으며 Azure 구독에서 Microsoft 365 Azure AD 테넌트에 액세스하려는 경우 [Azure Active Directory 테넌트에 기존의 Azure 구독을 추가](/azure/active-directory/fundamentals/active-directory-how-subscriptions-associated-directory)의 지침을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-201">If you purchased Azure and Microsoft 365 subscriptions separately and want to access the Microsoft 365 Azure AD tenant from your Azure subscription, see the instructions in [Add an existing Azure subscription to your Azure Active Directory tenant](/azure/active-directory/fundamentals/active-directory-how-subscriptions-associated-directory).</span></span>
 
## <a name="see-also"></a><span data-ttu-id="b0e8f-202">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b0e8f-202">See also</span></span>

[<span data-ttu-id="b0e8f-203">엔터프라이즈 설계자용 Microsoft 클라우드 일러스트레이션</span><span class="sxs-lookup"><span data-stu-id="b0e8f-203">Microsoft cloud for enterprise architects illustrations</span></span>](../solutions/cloud-architecture-models.md)
  
[<span data-ttu-id="b0e8f-204">Exchange, SharePoint, 비즈니스용 Skype 및 Lync에 대한 아키텍처 모델</span><span class="sxs-lookup"><span data-stu-id="b0e8f-204">Architectural models for SharePoint, Exchange, Skype for Business, and Lync</span></span>](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md)
  
[<span data-ttu-id="b0e8f-205">하이브리드 솔루션</span><span class="sxs-lookup"><span data-stu-id="b0e8f-205">Hybrid solutions</span></span>](hybrid-solutions.md)

## <a name="next-step"></a><span data-ttu-id="b0e8f-206">다음 단계</span><span class="sxs-lookup"><span data-stu-id="b0e8f-206">Next step</span></span>

[<span data-ttu-id="b0e8f-207">Microsoft 365 네트워크 연결 평가</span><span class="sxs-lookup"><span data-stu-id="b0e8f-207">Assessing Microsoft 365 network connectivity</span></span>](assessing-network-connectivity.md)
