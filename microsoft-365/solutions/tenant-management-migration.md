---
title: 4단계. 엔터프라이즈용 Microsoft 365 테넌트 마이그레이션
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: Microsoft 365 테넌트에 대한 Windows 장치, Office 클라이언트 앱 및 Office 서버를 마이그레이션합니다.
ms.openlocfilehash: 336dee2e62c6d0917c437252ba1d741c304998fa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929147"
---
# <a name="step-4-migration-for-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="c593a-104">4단계.</span><span class="sxs-lookup"><span data-stu-id="c593a-104">Step 4.</span></span> <span data-ttu-id="c593a-105">엔터프라이즈용 Microsoft 365 테넌트 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="c593a-105">Migration for your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="c593a-106">대부분의 엔터프라이즈 조직에는 여러 릴리스의 운영 체제, 클라이언트 소프트웨어 및 서버 소프트웨어가 포함된 다른 환경이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c593a-106">Most enterprise organizations have a heterogeneous environment that includes multiple releases of operating systems, client software, and server software.</span></span> <span data-ttu-id="c593a-107">엔터프라이즈용 Microsoft 365에는 IT 인프라의 주요 구성 요소 중 가장 안전한 버전이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c593a-107">Microsoft 365 for enterprise includes the most secure versions of the key components of your IT infrastructure.</span></span> <span data-ttu-id="c593a-108">클라우드 기술을 활용하도록 설계된 생산성 기능도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c593a-108">It also includes productivity features that are designed to take advantage of cloud technologies.</span></span>

<span data-ttu-id="c593a-109">엔터프라이즈용 Microsoft 365 통합 제품군의 비즈니스 가치를 극대화하려면 다음 릴리스를 마이그레이션하는 전략을 계획하고 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="c593a-109">To maximize the business value of the Microsoft 365 for enterprise integrated suite of products, begin planning and implementing a strategy to migrate these releases:</span></span>

| <span data-ttu-id="c593a-110">From</span><span class="sxs-lookup"><span data-stu-id="c593a-110">From</span></span> | <span data-ttu-id="c593a-111">받는 사람</span><span class="sxs-lookup"><span data-stu-id="c593a-111">To</span></span> |
|:-------|:-----|
| <span data-ttu-id="c593a-112">Windows 7 및 Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="c593a-112">Windows 7 and Windows 8.1</span></span> | <span data-ttu-id="c593a-113">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c593a-113">Windows 10 Enterprise</span></span> |
| <span data-ttu-id="c593a-114">직장의 장치에 설치된 Office 클라이언트 제품</span><span class="sxs-lookup"><span data-stu-id="c593a-114">Office client products installed on your worker's devices</span></span> | <span data-ttu-id="c593a-115">엔터프라이즈용 Microsoft 365 앱</span><span class="sxs-lookup"><span data-stu-id="c593a-115">Microsoft 365 Apps for enterprise</span></span> |
| <span data-ttu-id="c593a-116">Office server products installed on on-premises servers</span><span class="sxs-lookup"><span data-stu-id="c593a-116">Office server products installed on on-premises servers</span></span> | <span data-ttu-id="c593a-117">Microsoft 365의 동등한 클라우드 기반 서비스</span><span class="sxs-lookup"><span data-stu-id="c593a-117">Their equivalent cloud-based services in Microsoft 365</span></span> |
|  |  |

## <a name="migrating-to-windows-10"></a><span data-ttu-id="c593a-118">Windows 10으로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="c593a-118">Migrating to Windows 10</span></span>

<span data-ttu-id="c593a-119">각 엔터프라이즈용 Microsoft 365 라이선스에는 Windows 10 Enterprise용 라이선스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c593a-119">Each Microsoft 365 for enterprise license includes a license for Windows 10 Enterprise.</span></span> <span data-ttu-id="c593a-120">Windows 7 또는 Windows 8.1을 실행 하는 장치를 마이그레이션하려면 바로 업그레이드를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c593a-120">To migrate your devices that run Windows 7 or Windows 8.1, you can do an in-place upgrade.</span></span> <span data-ttu-id="c593a-121">*2020년 1월 14일* Windows 7에 대한 지원이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="c593a-121">Support ended for Windows 7 on *January 14, 2020*.</span></span> 

<span data-ttu-id="c593a-122">전체 업그레이드를 넘어 Windows 10 Enterprise를 설치하는 추가 방법은 [Windows 10 배포 시나리오를 참조합니다.](/windows/deployment/windows-10-deployment-scenarios)</span><span class="sxs-lookup"><span data-stu-id="c593a-122">For additional methods of installing Windows 10 Enterprise beyond an in-place upgrade, see [Windows 10 deployment scenarios](/windows/deployment/windows-10-deployment-scenarios).</span></span> <span data-ttu-id="c593a-123">직접 [Windows 10 배포를 계획](/windows/deployment/planning/)할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c593a-123">You can also [plan for Windows 10 deployment](/windows/deployment/planning/) on your own.</span></span>

## <a name="migrating-to-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="c593a-124">엔터프라이즈용 Microsoft 365 앱으로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="c593a-124">Migrating to Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="c593a-125">엔터프라이즈용 Microsoft 365에는 Microsoft 클라우드에서 설치 및 업데이트되는 Office 클라이언트 제품 버전(Word, PowerPoint, Excel 및 Outlook)인 엔터프라이즈용 Microsoft 365 앱이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c593a-125">Microsoft 365 for enterprise includes Microsoft 365 Apps for enterprise, a version of the Office client products (Word, PowerPoint, Excel, and Outlook) that is installed and updated from the Microsoft cloud.</span></span> <span data-ttu-id="c593a-126">자세한 내용은 [엔터프라이즈용 Microsoft 365 앱 정보를 참조하세요.](/deployoffice/about-microsoft-365-apps)</span><span class="sxs-lookup"><span data-stu-id="c593a-126">For more information, see [About Microsoft 365 Apps for enterprise](/deployoffice/about-microsoft-365-apps).</span></span>

<span data-ttu-id="c593a-127">컴퓨터를 Office 2019 또는 이전 버전에 대해 최신으로 유지하는 대신 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c593a-127">Rather than keeping your computers current for Office 2019 or older versions, take the following steps:</span></span>

1. <span data-ttu-id="c593a-128">사용자에 대한 Microsoft 365 라이선스를 다운로드하고 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="c593a-128">Get and assign a Microsoft 365 license for your users.</span></span>
2. <span data-ttu-id="c593a-129">컴퓨터에서 Office 2013 또는 Office 2016을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="c593a-129">Uninstall Office 2013 or Office 2016 on their computers.</span></span>
3. <span data-ttu-id="c593a-130">개별적으로 또는 IT 롤아웃 중에 엔터프라이즈용 Microsoft 365 앱을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="c593a-130">Install Microsoft 365 Apps for enterprise, either individually or during an IT rollout.</span></span> <span data-ttu-id="c593a-131">자세한 내용은 Microsoft 365 앱 배포 [가이드를 참조하세요.](/deployoffice/deployment-guide-microsoft-365-apps)</span><span class="sxs-lookup"><span data-stu-id="c593a-131">For more information, see [Deployment guide for Microsoft 365 Apps](/deployoffice/deployment-guide-microsoft-365-apps).</span></span>

<span data-ttu-id="c593a-132">엔터프라이즈용 Microsoft 365 앱은 보안 업데이트와 새로운 기능 업데이트를 자동으로 설치하며 Microsoft 365의 클라우드 기반 서비스를 사용하여 향상된 보안 및 생산성을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c593a-132">Microsoft 365 Apps for enterprise installs both security updates and new feature updates automatically and can take advantage of cloud-based services in Microsoft 365 for enhanced security and productivity.</span></span>

## <a name="migrating-on-premises-servers-and-data-to-microsoft-365"></a><span data-ttu-id="c593a-133">Microsoft 365로의 사내 서버 및 데이터 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="c593a-133">Migrating on-premises servers and data to Microsoft 365</span></span>

<span data-ttu-id="c593a-134">엔터프라이즈용 Microsoft 365에는 웹 브라우저 및 Outlook 클라이언트와 같은 Office 서버 소프트웨어의 일부와 동일한 도구 중 일부를 사용하는 클라우드 기반 버전의 Office 서버 서비스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c593a-134">Microsoft 365 for enterprise includes cloud-based versions of Office server services that use some of the same tools as on-premises versions of Office server software, such as web browsers and the Outlook client.</span></span> <span data-ttu-id="c593a-135">이러한 클라우드 기반 서비스는 보안 및 새 기능을 위해 자동으로 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="c593a-135">These cloud-based services are automatically updated for security and new features.</span></span> <span data-ttu-id="c593a-136">마이그레이션 후 IT 부서에서 사내 서버를 유지 관리하고 업데이트하는 데 걸리는 시간을 절약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c593a-136">After migration, your IT department can save the time it takes to maintain and update on-premises servers.</span></span>

<span data-ttu-id="c593a-137">특정 Microsoft 365 워크로드에 대한 사용자 및 데이터를 마이그레이션하는 데 대한 정보는 다음 리소스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c593a-137">Use the following resources for information about migrating users and data for specific Microsoft 365 workloads:</span></span>

- [<span data-ttu-id="c593a-138">사서함을 Exchange Online으로 Exchange Server 사서함 이동</span><span class="sxs-lookup"><span data-stu-id="c593a-138">Move mailboxes from on-premises Exchange Server to Exchange Online</span></span>](/exchange/hybrid-deployment/move-mailboxes)
- [<span data-ttu-id="c593a-139">SharePoint Server에서 SharePoint Online으로 SharePoint 데이터 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="c593a-139">Migrate SharePoint data from SharePoint Server to SharePoint Online</span></span>](/sharepointmigration/migrate-to-sharepoint-online)
- [<span data-ttu-id="c593a-140">비즈니스용 Skype Online을 Microsoft Teams로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="c593a-140">Migrate Skype for Business Online to Microsoft Teams</span></span>](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

## <a name="transition-your-entire-organization"></a><span data-ttu-id="c593a-141">전체 조직 전환</span><span class="sxs-lookup"><span data-stu-id="c593a-141">Transition your entire organization</span></span>

<span data-ttu-id="c593a-142">전체 조직을 엔터프라이즈용 Microsoft 365의 제품 및 서비스로 이동하는 방법을 더 잘 확인하려면 다음 전환 포스터를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="c593a-142">To get a better picture of how to move your entire organization to the products and services in Microsoft 365 for enterprise, download this transition poster:</span></span>

<span data-ttu-id="c593a-143">[![Microsoft 365로 전환 포스터를 보여주는 이미지.](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)</span><span class="sxs-lookup"><span data-stu-id="c593a-143">[![Image showing the Transition to Microsoft 365 poster.](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)</span></span>

<span data-ttu-id="c593a-144">이 두 페이지 포스터는 기존 인프라를 신속하게 인벤터리하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="c593a-144">This two-page poster is a quick way to inventory your existing infrastructure.</span></span> <span data-ttu-id="c593a-145">엔터프라이즈용 Microsoft 365에서 제품 또는 서비스로 이동하기 위한 지침을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="c593a-145">Use it to get guidance for moving to a product or service in Microsoft 365 for enterprise.</span></span> <span data-ttu-id="c593a-146">Windows 및 Office 제품 및 기타 인프라 및 보안 요소(예: 장치 관리, ID 및 위협 방지, 정보 보호 및 규정 준수)를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="c593a-146">It shows Windows and Office products and other infrastructure and security elements such as device management, identity and threat protection, and information protection and compliance.</span></span>

## <a name="results-of-step-4"></a><span data-ttu-id="c593a-147">4단계의 결과</span><span class="sxs-lookup"><span data-stu-id="c593a-147">Results of Step 4</span></span>

<span data-ttu-id="c593a-148">Microsoft 365 테넌트에 대한 마이그레이션의 경우 다음을 결정했습니다.</span><span class="sxs-lookup"><span data-stu-id="c593a-148">For migration for your Microsoft 365 tenant, you have determined:</span></span>

- <span data-ttu-id="c593a-149">Windows 7 또는 Windows 8.1을 실행 중인 디바이스와 Windows 10 Enterprise로 업데이트할 계획입니다.</span><span class="sxs-lookup"><span data-stu-id="c593a-149">Which devices are running Windows 7 or Windows 8.1 and the plan to update them to Windows 10 Enterprise.</span></span>
- <span data-ttu-id="c593a-150">Office 클라이언트 앱을 실행 중인 장치 및 엔터프라이즈용 Microsoft 365 앱으로 업데이트할 계획입니다.</span><span class="sxs-lookup"><span data-stu-id="c593a-150">Which devices are running the Office client apps and the plan to update them to Microsoft 365 apps for enterprise.</span></span>
- <span data-ttu-id="c593a-151">Microsoft 365에 해당하는 서비스로 마이그레이션해야 하는 사내 Office 서버 서비스와 해당 서비스 및 해당 데이터를 마이그레이션하기 위한 계획</span><span class="sxs-lookup"><span data-stu-id="c593a-151">Which on-premises Office server services should be migrated to their Microsoft 365 equivalent and the plan to migrate them and their data.</span></span>

<span data-ttu-id="c593a-152">다음은 전체 마이그레이션이 완료된 테넌트의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="c593a-152">Here is an example of a tenant with a completed migration of on-premises servers.</span></span>

![완료된 마이그레이션을 완료한 테넌트의 예](../media/tenant-management-overview/tenant-management-tenant-build-step4.png)

<span data-ttu-id="c593a-154">이 그림에서 조직은 다음을 하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c593a-154">In this illustration, the organization has:</span></span>

- <span data-ttu-id="c593a-155">해당 사서함의 Exchange Server Exchange Online으로 마이그레이션했습니다.</span><span class="sxs-lookup"><span data-stu-id="c593a-155">Migrated its on-premises Exchange Server mailboxes to Exchange Online.</span></span>
- <span data-ttu-id="c593a-156">Microsoft 365의 SharePoint로 해당 사내 SharePoint Server 사이트 및 데이터를 마이그레이션했습니다.</span><span class="sxs-lookup"><span data-stu-id="c593a-156">Migrated its on-premises SharePoint Server sites and data to SharePoint in Microsoft 365.</span></span>

## <a name="ongoing-maintenance-for-migration"></a><span data-ttu-id="c593a-157">마이그레이션을 위한 지속적인 유지 관리</span><span class="sxs-lookup"><span data-stu-id="c593a-157">Ongoing maintenance for migration</span></span>

<span data-ttu-id="c593a-158">지속적인 기준에 따라 다음을 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c593a-158">On an ongoing basis, you might need to:</span></span>

- <span data-ttu-id="c593a-159">Exchange 사서함 마이그레이션의 상태에 따라 Exchange Online으로의 전환을 조직에 계속 롤아웃합니다.</span><span class="sxs-lookup"><span data-stu-id="c593a-159">Depending on the state of your Exchange mailbox migration, continue rolling the transition to Exchange Online out to your organization.</span></span>
- <span data-ttu-id="c593a-160">사내 SharePoint 사이트 마이그레이션의 상태에 따라 Microsoft 365의 SharePoint로의 전환을 조직에 계속 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="c593a-160">Depending on the state of your on-premises SharePoint site migration, continue rolling the transition to SharePoint in Microsoft 365 out to your organization.</span></span>

## <a name="next-step"></a><span data-ttu-id="c593a-161">다음 단계</span><span class="sxs-lookup"><span data-stu-id="c593a-161">Next step</span></span>

<span data-ttu-id="c593a-162">[![5단계. 장치 및 앱 관리 배포](../media/tenant-management-overview/tenant-management-step-grid-device-mgmt.png)](tenant-management-device-management.md)</span><span class="sxs-lookup"><span data-stu-id="c593a-162">[![Step 5. Deploy device and app management](../media/tenant-management-overview/tenant-management-step-grid-device-mgmt.png)](tenant-management-device-management.md)</span></span>

<span data-ttu-id="c593a-163">장치 및 [앱 관리를 계속하여](tenant-management-device-management.md) 장치 및 앱 관리를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="c593a-163">Continue with [device and app management](tenant-management-device-management.md) to deploy device and app management.</span></span>