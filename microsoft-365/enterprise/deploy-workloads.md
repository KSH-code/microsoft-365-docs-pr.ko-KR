---
title: Microsoft 365 Enterprise 워크로드
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/15/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 조직의 사용자에게 Microsoft 365 Enterprise의 생산성 워크로드를 제공합니다.
ms.openlocfilehash: 0e1658655c4b97a7e571d1ac09c4b2edcc6c82ce
ms.sourcegitcommit: 47c45bd81afdc4867ff2980ced3df31dbad92b84
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268288"
---
# <a name="microsoft-365-for-enterprise-workloads"></a><span data-ttu-id="91722-103">Microsoft 365 Enterprise 워크로드</span><span class="sxs-lookup"><span data-stu-id="91722-103">Microsoft 365 for enterprise workloads</span></span>

<span data-ttu-id="91722-104">Microsoft 365 Enterprise의 독창성과 팀워크 이점을 얻으려면 기본 인프라에 다음과 같은 워크로드를 배포하세요.</span><span class="sxs-lookup"><span data-stu-id="91722-104">To get the creativity and teamwork benefits of Microsoft 365 for enterprise, deploy these workloads over your foundation infrastructure:</span></span>

- [<span data-ttu-id="91722-105">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="91722-105">Microsoft Teams</span></span>](teams-workload.md)
- [<span data-ttu-id="91722-106">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="91722-106">Exchange Online</span></span>](exchangeonline-workload.md)
- [<span data-ttu-id="91722-107">SharePoint 및 OneDrive</span><span class="sxs-lookup"><span data-stu-id="91722-107">SharePoint and OneDrive</span></span>](sharepoint-online-onedrive-workload.md)

<span data-ttu-id="91722-108">전체 조직을 Microsoft Office 클라이언트 제품, 온-프레미스 Office Server 제품 및 Microsoft Windows 기반 장치가 포함된 Microsoft 365 Enterprise로 마이그레이션하는 일반적인 로드맵은 [마이그레이션](migration-microsoft-365-enterprise-workload.md) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="91722-108">See the [migration](migration-microsoft-365-enterprise-workload.md) article for a general roadmap to migrate your entire organization to Microsoft 365 for enterprise, which includes Microsoft Office client products, on-premises Office Server products, and Microsoft Windows-based devices.</span></span>

<span data-ttu-id="91722-109">전체 Microsoft 365 Enterprise 배포 가이드의 워크로드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="91722-109">Here are the workloads in the overall Microsoft 365 for enterprise deployment guide:</span></span>

![전체 Microsoft 365 Enterprise 배포 가이드의 워크로드](../media/deploy-workloads/m365-deploy-content-arch-workloads.png)

## <a name="foundation-infrastructure-prerequisites"></a><span data-ttu-id="91722-111">기본 인프라 전제 조건</span><span class="sxs-lookup"><span data-stu-id="91722-111">Foundation infrastructure prerequisites</span></span>

<span data-ttu-id="91722-112">*이상적으로*는 [기초 인프라](deploy-foundation-infrastructure.md)의 모든 단계를 구성한 후에 워크로드를 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91722-112">*Ideally*, you should deploy workloads after you have configured all of the phases of the [foundation infrastructure](deploy-foundation-infrastructure.md).</span></span> <span data-ttu-id="91722-113">이렇게하면 모든 기본 기반 계층이 사용자 및 장치에 통합, 보안 및 최상의 환경을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91722-113">This ensures that all of the underlying foundation layers are in place to provide integration, security, and the best experience for your users and their devices.</span></span>

| <span data-ttu-id="91722-114">단계</span><span class="sxs-lookup"><span data-stu-id="91722-114">Phase</span></span> | <span data-ttu-id="91722-115">결과</span><span class="sxs-lookup"><span data-stu-id="91722-115">Result</span></span> |
|:-------|:-----|
| <span data-ttu-id="91722-116">네트워크</span><span class="sxs-lookup"><span data-stu-id="91722-116">Network</span></span> | <span data-ttu-id="91722-117">네트워크가 Microsoft 365 클라우드 서비스에 최적의 성능을 발휘하도록 업데이트 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="91722-117">Your network is updated for optimum performance to Microsoft 365 cloud services.</span></span> |
| <span data-ttu-id="91722-118">ID</span><span class="sxs-lookup"><span data-stu-id="91722-118">Identity</span></span> | <span data-ttu-id="91722-119">ID는 사용자 계정에 대한 강력한 인증과 관리자 계정에 대한 보호로 동기화되고 안전하게 보호됩니다.</span><span class="sxs-lookup"><span data-stu-id="91722-119">Identity is synchronized and secured with strong authentication for user accounts and protection for admin accounts.</span></span> |
| <span data-ttu-id="91722-120">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="91722-120">Windows 10 Enterprise</span></span> | <span data-ttu-id="91722-121">Windows 7 또는 Windows 8.1을 실행하는 컴퓨터는 Windows 10 Enterprise로 업그레이드 할 수 있으며 새 장치는 Windows 10 Enterprise가 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="91722-121">Your computers running Windows 7 or Windows 8.1 can upgrade to Windows 10 Enterprise and new devices are installed with Windows 10 Enterprise.</span></span> |
| <span data-ttu-id="91722-122">엔터프라이즈용 Microsoft 365 앱</span><span class="sxs-lookup"><span data-stu-id="91722-122">Microsoft 365 Apps for enterprise</span></span> | <span data-ttu-id="91722-123">Microsoft Office의 기존 사용자는 엔터프라이즈용 Microsoft 365 앱으로 업그레이드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91722-123">Your existing users of Microsoft Office can upgrade to Microsoft 365 Apps for enterprise.</span></span> |
| <span data-ttu-id="91722-124">모바일 장치 관리</span><span class="sxs-lookup"><span data-stu-id="91722-124">Mobile device management</span></span> | <span data-ttu-id="91722-125">장치를 등록하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91722-125">Your devices can be enrolled and managed.</span></span> |
| <span data-ttu-id="91722-126">정보 보호</span><span class="sxs-lookup"><span data-stu-id="91722-126">Information protection</span></span> | <span data-ttu-id="91722-127">Office 365 정보 보호 기능이 구성되고 민감도 또는 Azure 정보 보호 레이블은 문서와 이메일을 보호할 준비가 되어있습니다.</span><span class="sxs-lookup"><span data-stu-id="91722-127">Microsoft 365 information protection features are configured and your sensitivity or Azure Information Protection labels are ready to protect documents and email.</span></span> |

<span data-ttu-id="91722-128">이는 이상적이며 특히 기존 인프라 및 여러 위치를 가진 대규모 조직에서 구성, 테스트 및 파일럿 수행을 계획하는 데 시간이 걸릴 수 있음을 기억하세요.</span><span class="sxs-lookup"><span data-stu-id="91722-128">Remember that this is ideal and can take some time to plan for, configure, test, and pilot, especially in large organizations with existing infrastructure and multiple locations.</span></span> <span data-ttu-id="91722-129">Microsoft 365 Enterprise에서 비즈니스 가치를 더 빨리 얻기 위해 모든 위치에서 이러한 단계를 완료할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="91722-129">Completing all of these phases in all locations is not necessary for you to more quickly get business value from Microsoft 365 for enterprise.</span></span> 

<span data-ttu-id="91722-130">다음은 몇 가지 일반적인 워크로드를 즉시 배포하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="91722-130">Here are some common workloads to deploy right away:</span></span> 

- <span data-ttu-id="91722-131">기본 인프라의 **ID** 단계가 사용자에게 배포되면 많은 조직이 다음을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="91722-131">After the **Identity** phase of the foundation infrastructure is rolled out to users, many organizations deploy:</span></span>
  - <span data-ttu-id="91722-132">[OneDrive](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise)와 함께 사용된 [엔터프라이즈용 Microsoft 365 앱](office365proplus-infrastructure.md)</span><span class="sxs-lookup"><span data-stu-id="91722-132">[Microsoft 365 Apps for enterprise](office365proplus-infrastructure.md) combined with [OneDrive](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise).</span></span> <span data-ttu-id="91722-133">엔터프라이즈용 Microsoft 365 앱은 최신 인증 보안 및 최신 Microsoft Office 클라이언트 사용자 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="91722-133">Microsoft 365 Apps for enterprise provides the security of modern authentication and the user experience of the latest Microsoft Office client.</span></span> <span data-ttu-id="91722-134">사용자 개인 파일을 OneDrive로 마이그레이션하면 홈 폴더 및 드라이브를 지원해야 할 필요성과 인프라가 줄어 듭니다.</span><span class="sxs-lookup"><span data-stu-id="91722-134">The migration of user's personal files to OneDrive reduces infrastructure and the need to support home folders and drives.</span></span>
  - <span data-ttu-id="91722-135">[Exchange Online](exchangeonline-workload.md)을 사용하면 사용자가 클라우드 기반 이메일을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91722-135">[Exchange Online](exchangeonline-workload.md) so that users can begin using cloud-based email.</span></span>
- <span data-ttu-id="91722-136">엄격히 규제된 디지털 자산을 클라우드에 즉시 저장할 필요가 없다면 **정보 보호** 단계 이전에 [Microsoft Teams](teams-workload.md) 및 [SharePoint](sharepoint-online-onedrive-workload.md)를 사용자에게 배포하세요.</span><span class="sxs-lookup"><span data-stu-id="91722-136">If you don't have an immediate need for storing highly regulated digital assets in the cloud, deploy [Microsoft Teams](teams-workload.md) and [SharePoint](sharepoint-online-onedrive-workload.md) for your users prior to the **Information protection** phase.</span></span>

<span data-ttu-id="91722-137">비즈니스 요구 사항을 충족시킬 수 있도록 기본 인프라의 전제 조건 단계를 구성하는 데 가장 적합한 방법을 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91722-137">You must decide on how to best order and deploy the configuration of prerequisite phases of foundation infrastructure to meet your business needs.</span></span>

### <a name="best-practice"></a><span data-ttu-id="91722-138">모범 사례</span><span class="sxs-lookup"><span data-stu-id="91722-138">Best practice</span></span>

<span data-ttu-id="91722-139">사용자를 모든 워크로드 또는 시나리오에 온 보딩하기 전에 기본 인프라의 **ID** 단계를 배포하고 롤아웃하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="91722-139">We highly recommend that you deploy and roll out the **Identity** phase of the foundation infrastructure prior to onboarding your users to any workloads or scenarios.</span></span>

<span data-ttu-id="91722-140">**ID** 단계에서는 클라우드 전용 또는 온-프레미스 AD DS (Active Directory 도메인 서비스)와 동기화 된 클라우드 기반 ID에 인증 및 액세스를 관리 할 사용자 및 컴퓨터 계정과 그룹이 포함되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="91722-140">The **Identity** phase ensures that your cloud-based identity, whether cloud-only or synchronized with your on-premises Active Directory Domain Services (AD DS), contains the user and computer accounts and groups to manage authentication and access.</span></span> <span data-ttu-id="91722-141">조직의 디지털 자산을 Microsoft 365 클라우드에 배치하기 전에 관리자 계정을 강력하게 보호하고 모든 사용자에 대해 강력한 인증을 수행해야합니다.</span><span class="sxs-lookup"><span data-stu-id="91722-141">Strong authentication for all your users along with strong protection of admin accounts is required before placing your organization's digital assets in the Microsoft 365 cloud.</span></span>

<span data-ttu-id="91722-142">전반적인 성능에 있어 기본적이고 매우 중요하지만 Microsoft 365 작업 부하 및 서비스 성능이 시간이 지남에 따라 개선될 것이라는 점을 고려하여 사용자를작업 부하에 적응 시키는 동안 **네트워킹** 단계가 진행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91722-142">Although foundational and very important to overall performance, the rollout of the **Networking** phase can be in progress while onboarding your users to workloads, with the understanding that Microsoft 365 workload and service performance will improve over time.</span></span> <span data-ttu-id="91722-143">이는 여러 위치가 있고 에지 장치와 인터넷 연결이 혼합된 엔터프라이즈 조직에 특히 해당됩니다.</span><span class="sxs-lookup"><span data-stu-id="91722-143">This is especially true for enterprise organizations with multiple locations and a mixture of edge devices and Internet connections.</span></span>
