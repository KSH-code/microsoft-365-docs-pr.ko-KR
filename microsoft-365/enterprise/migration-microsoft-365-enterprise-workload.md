---
title: Microsoft 365 Enterprise로 마이그레이션
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: 조직 전체에서 Microsoft Office, Office 서버 및 Windows 버전을 Microsoft 365 Enterprise로 마이그레이션하는 프로세스를 단계별로 안내합니다.
ms.openlocfilehash: 06cacbb45a98bb62f53866b0d2ab7ba393e609a0
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633246"
---
# <a name="migration-to-microsoft-365-enterprise"></a><span data-ttu-id="19257-103">Microsoft 365 Enterprise로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="19257-103">Migration to Microsoft 365 Enterprise</span></span>

<span data-ttu-id="19257-p101">대부분의 엔터프라이즈 조직은 여러 릴리스의 운영 체제, 클라이언트 소프트웨어 및 서버 소프트웨어가 섞여 있는 이기종 환경을 사용하고 있습니다. Microsoft 365 Enterprise에는 클라우드 기술을 활용하도록 고안된 생산성 기능과 이러한 IT 인프라의 가장 안전한 핵심 구성 요소 버전이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19257-p101">Most enterprise organizations have a heterogeneous environment with multiple releases of operating systems, client software, and server software. Microsoft 365 Enterprise includes the most secure versions of these key components of your IT infrastructure with productivity features that are designed to take advantage of cloud technologies.</span></span>

<span data-ttu-id="19257-106">Microsoft 365 Enterprise 통합 제품군의 비즈니스 가치를 최대화하려면 다음 릴리스를 마이그레이션하기 위한 계획을 세우고 전략을 구현하세요.</span><span class="sxs-lookup"><span data-stu-id="19257-106">To maximize the business value of the Microsoft 365 Enterprise integrated suite of products, begin planning and implementing a strategy to migrate releases of:</span></span>

- <span data-ttu-id="19257-107">컴퓨터에 설치된 Office 클라이언트를 Office 365 ProPlus로</span><span class="sxs-lookup"><span data-stu-id="19257-107">The Office client installed on your computers to Office 365 ProPlus</span></span>
- <span data-ttu-id="19257-108">서버에 설치된 Office 서버를 Office 365의 해당 서비스로</span><span class="sxs-lookup"><span data-stu-id="19257-108">Office servers installed on your servers to their equivalent services in Office 365</span></span>
- <span data-ttu-id="19257-109">장치의 Windows 7 및 Windows 8.1을 Windows 10 Enterprise로</span><span class="sxs-lookup"><span data-stu-id="19257-109">Windows 7 and Windows 8.1 on your devices to Windows 10 Enterprise</span></span>

>[!Note]
><span data-ttu-id="19257-110">Windows 7은 **2020년 1월 14일**에 지원이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="19257-110">Windows 7 reaches end of support on **January 14, 2020**.</span></span> <span data-ttu-id="19257-111">자세한 내용은 [여기](https://support.microsoft.com/help/4057281/windows-7-support-will-end-on-january-14-2020)를 클릭하세요.</span><span class="sxs-lookup"><span data-stu-id="19257-111">For more information, click [here](https://support.microsoft.com/help/4057281/windows-7-support-will-end-on-january-14-2020).</span></span>
>

<span data-ttu-id="19257-112">시간이 지나면서 조직에서 이러한 모든 마이그레이션을 완료하게 되면 Microsoft 365 Enterprise를 통해 조직의 팀워크와 창의성이 극대화되는 보안 통합형 [최신 작업 환경](https://www.microsoft.com/microsoft-365/blog/2018/04/27/making-it-simpler-with-a-modern-workplace/)에 더 가까워지게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="19257-112">Accomplishing all of these migrations over time gets your organization closer to the [modern workplace](https://www.microsoft.com/microsoft-365/blog/2018/04/27/making-it-simpler-with-a-modern-workplace/), a secure and integrated environment that unlocks teamwork and creativity in your organization, all of which is enabled and empowered by Microsoft 365 Enterprise.</span></span> 

<span data-ttu-id="19257-113">특정 Office 365 워크로드에 대한 사용자 및 데이터 마이그레이션에 대한 자세한 내용은 다음을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="19257-113">For information about migrating users and data for specific Office 365 workloads:</span></span>

- <span data-ttu-id="19257-114">Exchange Server에서 Exchange Online으로 마이그레이션하는 사용자 메일함은 [Exchange Online 워크로드](exchangeonline-workload.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="19257-114">User mailboxes from Exchange Server to Exchange Online, see the [Exchange Online workload](exchangeonline-workload.md).</span></span>
- <span data-ttu-id="19257-115">SharePoint Server에서 SharePoint Online으로 마이그레이션하는 SharePoint 데이터는 [SharePoint Online 워크로드](sharepoint-online-onedrive-workload.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="19257-115">SharePoint data from SharePoint Server to SharePoint Online, see the [SharePoint Online workload](sharepoint-online-onedrive-workload.md).</span></span>
- <span data-ttu-id="19257-116">비즈니스용 Skype Online을 Microsoft Teams으로 마이그레이션시 [Microsoft Teams 워크로드](teams-workload.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="19257-116">Skype for Business Online to Microsoft Teams, see the [Microsoft Teams workload](teams-workload.md).</span></span>

## <a name="migration-for-microsoft-office-client-products"></a><span data-ttu-id="19257-117">Microsoft Office 클라이언트 제품에 대한 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="19257-117">Migration for Microsoft Office client products</span></span>

<span data-ttu-id="19257-p103">많은 대기업 및 중소기업에서는 Word, Excel 및 PowerPoint와 같은 이전 버전의 Office 클라이언트 제품 버전을 조합해서 사용하고 있을 것입니다. 이러한 이전 버전은 다음과 같을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19257-p103">In many organizations both large and small, you might be using a combination of older versions of the Office client products, such as Word, Excel, and PowerPoint. These older versions:</span></span>

- <span data-ttu-id="19257-120">최신 보안 업데이트 및 지원 수정 프로그램으로 [업데이트](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5)할 수 있지만 경우에 따라 이 프로세스가 수동으로 수행되며 조직 전체 규모로 진행되지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19257-120">Can be [updated](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5) with the latest security updates and support fixes, but the process is sometimes manual and might not scale across your organization.</span></span>
- <span data-ttu-id="19257-121">Microsoft의 클라우드 기술을 활용하여 비즈니스의 디지털 혁신을 이룰 수 있도록 최적화되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="19257-121">Are not optimally enabled to leverage Microsoft’s cloud technologies and help you digitally transform your business.</span></span>
- <span data-ttu-id="19257-122">새로운 기능이 포함되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="19257-122">Do not contain new features.</span></span>
 
<span data-ttu-id="19257-123">Microsoft 365 Enterprise에는 Microsoft 365 Enterprise 라이선스로 사용할 수 있고 Microsoft 클라우드에서 설치 및 업데이트되는 Office 클라이언트 제품 버전인 Office 365 ProPlus가 포함되어 있습니다. </span><span class="sxs-lookup"><span data-stu-id="19257-123">Microsoft 365 Enterprise includes Office 365 ProPlus, a version of the Office client products that is available with a Microsoft 365 Enterprise license and is installed and updated from the Microsoft cloud.</span></span> <span data-ttu-id="19257-124">Office 365 ProPlus에는 보안 업데이트와 최신 기능이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19257-124">Office 365 ProPlus includes security updates and the latest features.</span></span> <span data-ttu-id="19257-125">자세한 내용은 [엔터프라이즈의 Office 365 ProPlus](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="19257-125">See [About Office 365 ProPlus in the enterprise](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise) for more information.</span></span>

### <a name="office-2007"></a><span data-ttu-id="19257-126">Office 2007</span><span class="sxs-lookup"><span data-stu-id="19257-126">Office 2007</span></span>

<span data-ttu-id="19257-p105">Office 2007 릴리스에 포함된 Office 버전의 경우 지원 종료 기간이 이미 지났습니다. 자세한 내용은 [Office 2007 지원 종료 로드맵](https://docs.microsoft.com/deployoffice/office-2007-end-support-roadmap)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="19257-p105">For versions of Office in the Office 2007 release, the end of support has already passed. See [Office 2007 End of Support Roadmap](https://docs.microsoft.com/deployoffice/office-2007-end-support-roadmap) for more information.</span></span>

<span data-ttu-id="19257-129">Office 2007을 실행하는 컴퓨터를 Office 2010, Office 2013 또는 Office 2016으로 업그레이드하는 대신, 다음을 수행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="19257-129">Rather than upgrading your computers running Office 2007 with Office 2010, Office 2013, or Office 2016, consider:</span></span>

1. <span data-ttu-id="19257-130">사용자를 위한 Microsoft 365 라이선스 획득 및 할당</span><span class="sxs-lookup"><span data-stu-id="19257-130">Obtaining and assigning a Microsoft 365 license for your users.</span></span>
2. <span data-ttu-id="19257-131">컴퓨터에서 Office 2007 제거</span><span class="sxs-lookup"><span data-stu-id="19257-131">Uninstalling Office 2007 on their computers.</span></span>
3. <span data-ttu-id="19257-p106">개별적으로 또는 IT 롤아웃 작업과 함께 Office 365 ProPlus 설치. 자세한 내용은 [4단계: Office 365 ProPlus](office365proplus-infrastructure.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="19257-p106">Installing Office 365 ProPlus, either individually or in conjunction with an IT rollout. For more information, see [Phase 4: Office 365 ProPlus](office365proplus-infrastructure.md).</span></span>

<span data-ttu-id="19257-134">Office 365 ProPlus는 업데이트를 자동으로 설치하고 Office 365의 클라우드 기반 서비스를 활용하여 향상된 보안 및 생산성을 누릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19257-134">Office 365 ProPlus installs updates automatically and can take advantage of cloud-based services in Office 365 for enhanced security and productivity.</span></span>

### <a name="office-2010"></a><span data-ttu-id="19257-135">Office 2010</span><span class="sxs-lookup"><span data-stu-id="19257-135">Office 2010</span></span>

<span data-ttu-id="19257-136">Office 2010 릴리스에 있는 Office 버전의 경우에는 **2020년 10월 13일**에 지원이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="19257-136">For versions of Office in the Office 2010 release, the end of support is **October 13, 2020**.</span></span> <span data-ttu-id="19257-137">자세한 내용은 [Office 2010 지원 종료 로드맵](https://docs.microsoft.com/deployoffice/office-2010-end-support-roadmap)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="19257-137">For more information, see [Office 2010 end of support roadmap](https://docs.microsoft.com/deployoffice/office-2010-end-support-roadmap).</span></span>

<span data-ttu-id="19257-138">Office 2010을 실행하는 컴퓨터를 Office 2013 또는 Office 2016으로 업그레이드하는 대신(둘 다 수동으로 업데이트해야 함), 다음을 수행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="19257-138">Rather than upgrading your computers running Office 2010 with Office 2013 or Office 2016, both of which must be manually updated, consider:</span></span> 

1. <span data-ttu-id="19257-139">사용자를 위한 Microsoft 365 라이선스 획득 및 할당</span><span class="sxs-lookup"><span data-stu-id="19257-139">Obtaining and assigning a Microsoft 365 license for your users.</span></span>
2. <span data-ttu-id="19257-140">컴퓨터에서 Office 2010 제거</span><span class="sxs-lookup"><span data-stu-id="19257-140">Uninstalling Office 2010 on their computers.</span></span>
3. <span data-ttu-id="19257-p108">개별적으로 또는 IT 롤아웃 작업과 함께 Office 365 ProPlus 설치. 자세한 내용은 [4단계: Office 365 ProPlus](office365proplus-infrastructure.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="19257-p108">Installing Office 365 ProPlus, either individually or in conjunction with an IT rollout. For more information, see [Phase 4: Office 365 ProPlus](office365proplus-infrastructure.md).</span></span>

<span data-ttu-id="19257-143">Office 365 ProPlus는 보안 및 새로운 기능 업데이트를 자동으로 설치하고 Microsoft 365의 클라우드 기반 서비스를 활용하여 향상된 보안 및 생산성을 누릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19257-143">Office 365 ProPlus installs both security and new feature updates automatically and can take advantage of cloud-based services in Microsoft 365 for enhanced security and productivity.</span></span>

### <a name="office-2013-and-office-2016"></a><span data-ttu-id="19257-144">Office 2013 및 Office 2016</span><span class="sxs-lookup"><span data-stu-id="19257-144">Office 2013 and Office 2016</span></span>

<span data-ttu-id="19257-145">Office 2013 및 Office 2016 버전의 Office에 대한 지원 로드맵의 종료는 아직 확인되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="19257-145">The end of support roadmap for the Office 2013 and Office 2016 versions of Office has not yet been determined.</span></span> <span data-ttu-id="19257-146">그러나 Office 2010과 같이 [보안 업데이트를 설치](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5)해야 합니다. 이는 조직 규모에 따라 적절히 확장이 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19257-146">However, like Office 2010, you must still [install security updates](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5), which might not scale well depending on the size of your organization.</span></span>

<span data-ttu-id="19257-147">Office 2013 또는 Office 2016용 최신 보안 업데이트로 컴퓨터를 계속 업데이트하거나 Office 2013에서 Office 2016로 컴퓨터를 업데이트하는 대신 다음 사항을 고려해 보세요.</span><span class="sxs-lookup"><span data-stu-id="19257-147">Rather than keep updating your computers with the latest security updates for Office 2013 or Office 2016 or update your computers from Office 2013 to Office 2016, consider:</span></span>

1. <span data-ttu-id="19257-148">사용자를 위한 Microsoft 365 라이선스 획득 및 할당</span><span class="sxs-lookup"><span data-stu-id="19257-148">Obtaining and assigning a Microsoft 365 license for your users.</span></span>
2. <span data-ttu-id="19257-149">컴퓨터에서 Office 2013 또는 Office 2016을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="19257-149">Uninstalling Office 2013 or Office 2016 on their computers.</span></span>
3. <span data-ttu-id="19257-p110">개별적으로 또는 IT 롤아웃 작업과 함께 Office 365 ProPlus 설치. 자세한 내용은 [4단계: Office 365 ProPlus](office365proplus-infrastructure.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="19257-p110">Installing Office 365 ProPlus, either individually or in conjunction with an IT rollout. For more information, see [Phase 4: Office 365 ProPlus](office365proplus-infrastructure.md).</span></span>

<span data-ttu-id="19257-152">Office 365 ProPlus는 보안 및 새로운 기능 업데이트를 자동으로 설치하고 Microsoft 365의 클라우드 기반 서비스를 활용하여 향상된 보안 및 생산성을 누릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19257-152">Office 365 ProPlus installs both security and new feature updates automatically and can take advantage of cloud-based services in Microsoft 365 for enhanced security and productivity.</span></span>

## <a name="migration-for-microsoft-office-server-products"></a><span data-ttu-id="19257-153">Microsoft Office 서버 제품에 대한 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="19257-153">Migration for Microsoft Office server products</span></span>

<span data-ttu-id="19257-p111">많은 대기업 및 중소기업에서는 Exchange Server 및 SharePoint Server와 같은 이전 버전의 Office Server 제품 버전을 조합해서 사용하고 있을 것입니다. 이러한 이전 버전은 다음과 같을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="19257-p111">In many organizations both large and small, you might be using a combination of older versions of the Office Server products, such as Exchange Server and SharePoint Server. These older versions:</span></span>

- <span data-ttu-id="19257-p112">최신 보안 업데이트 및 지원 수정 프로그램으로 업데이트하는 것이 좋습니다. 경우에 따라 이러한 업데이트는 매월 출시됩니다.</span><span class="sxs-lookup"><span data-stu-id="19257-p112">Should be updated with the latest security updates and support fixes. In some cases, these updates are released monthly.</span></span>
- <span data-ttu-id="19257-158">Microsoft의 클라우드 기술을 활용하여 비즈니스의 디지털 혁신을 이룰 수 있도록 최적화되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="19257-158">Are not optimally enabled to leverage Microsoft’s cloud technologies and help you digitally transform your business.</span></span>
- <span data-ttu-id="19257-159">Microsoft Teams와 같은 새로운 생산성 응용 프로그램이 포함되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="19257-159">Do not include new productivity applications, such as Microsoft Teams.</span></span>
- <span data-ttu-id="19257-160">Exchange Advanced Threat Protection과 같은 최신 보안 기능이 포함되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="19257-160">Do not include the latest security features, such as Exchange Advanced Threat Protection.</span></span>

<span data-ttu-id="19257-161">Microsoft 365 Enterprise에는 웹 브라우저 및 Outlook 클라이언트와 같은 온-프레미스 버전의 Office 서버 소프트웨어와 동일한 도구 중 일부를 사용하는 클라우드 기반 Office server 서비스 버전을 포함하는 Office 365이 포함되어 있습니다. </span><span class="sxs-lookup"><span data-stu-id="19257-161">Microsoft 365 Enterprise includes Office 365, which includes cloud-based versions of Office server services that use some of the same tools as on-premises versions of Office server software, such as web browsers and the Outlook client.</span></span> <span data-ttu-id="19257-162">이러한 서비스는 IT 부서가 연관되지 않고도 보안을 위해 지속적으로 업데이트되므로 온-프레미스 서버를 유지 관리하고 업데이트하는 데 걸리는 시간이 절약됩니다.</span><span class="sxs-lookup"><span data-stu-id="19257-162">These services are continually updated for security without involving IT, saving you the time it takes to maintain and update on-premises servers.</span></span> <span data-ttu-id="19257-163">이러한 서비스에는 Office 서버 소프트웨어에 없는 새로운 기능 향상 기능도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19257-163">These services also have new features enhancements that are not present in Office server software.</span></span> 

### <a name="office-server-2007"></a><span data-ttu-id="19257-164">Office Server 2007</span><span class="sxs-lookup"><span data-stu-id="19257-164">Office Server 2007</span></span>

<span data-ttu-id="19257-p114">Office 2007 릴리스에 포함된 서버 제품의 경우 지원 종료 기한이 이미 경과되었습니다. 자세한 내용은 다음 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="19257-p114">For server products in the Office 2007 release, the end of support has already passed. See these articles for the details:</span></span>

- [<span data-ttu-id="19257-167">Exchange 2007 지원 종료 로드맵</span><span class="sxs-lookup"><span data-stu-id="19257-167">Exchange 2007 end of support roadmap</span></span>](https://docs.microsoft.com/office365/enterprise/exchange-2007-end-of-support)
- [<span data-ttu-id="19257-168">SharePoint Server 2007 지원 종료 로드맵</span><span class="sxs-lookup"><span data-stu-id="19257-168">SharePoint Server 2007 end of support roadmap</span></span>](https://docs.microsoft.com/office365/enterprise/sharepoint-2007-end-of-support)
- [<span data-ttu-id="19257-169">Project Server 2007 지원 종료 로드맵</span><span class="sxs-lookup"><span data-stu-id="19257-169">Project Server 2007 end of support roadmap</span></span>](https://docs.microsoft.com/office365/enterprise/project-server-2007-end-of-support)
- [<span data-ttu-id="19257-170">Office Communications Server 지원 종료 로드맵</span><span class="sxs-lookup"><span data-stu-id="19257-170">Office Communications Server end of support roadmap</span></span>](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/upgrade)
- [<span data-ttu-id="19257-171">PerformancePoint Server 2007 지원 종료 로드맵</span><span class="sxs-lookup"><span data-stu-id="19257-171">PerformancePoint Server 2007 end of support roadmap</span></span>](https://docs.microsoft.com/office365/enterprise/pps-2007-end-of-support)

<span data-ttu-id="19257-172">Office 2007 릴리스의 서버 제품을 Office 2010, Office 2013 또는 Office 2016 릴리스의 서버 제품으로 업그레이드하는 대신, 다음을 수행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="19257-172">Rather than upgrading your server products in the Office 2007 release with server products in the Office 2010, Office 2013, or Office 2016 releases, consider:</span></span>

1. <span data-ttu-id="19257-p115">Office 2007 서버의 데이터를 Office 365로 마이그레이션. 이를 지원하기 위해 Microsoft 파트너를 고용합니다.</span><span class="sxs-lookup"><span data-stu-id="19257-p115">Migrating the data on your Office 2007 servers to Office 365. To help with this, hire a Microsoft partner.</span></span>
2. <span data-ttu-id="19257-175">사용자에게 새 기능 및 작업 프로세스 롤아웃</span><span class="sxs-lookup"><span data-stu-id="19257-175">Rolling out the new functionality and work processes to your users.</span></span>
3. <span data-ttu-id="19257-176">Office 2007 서버 제품을 실행하는 온-프레미스 서버가 더 이상 필요하지 않은 경우 서비스 해제</span><span class="sxs-lookup"><span data-stu-id="19257-176">When there is no longer a need for the on-premises servers running Office 2007 server products, decommissioning them.</span></span>

### <a name="office-server-2010"></a><span data-ttu-id="19257-177">Office Server 2010</span><span class="sxs-lookup"><span data-stu-id="19257-177">Office Server 2010</span></span>

<span data-ttu-id="19257-178">Office 2010 릴리스 서버 제품의 경우 다음에 대한 지원 종료는 **2020년 10월 13일**입니다.</span><span class="sxs-lookup"><span data-stu-id="19257-178">For server products in the Office 2010 release, the end of support is **October 13, 2020** for the following:</span></span>

- [<span data-ttu-id="19257-179">Exchange Server 2010</span><span class="sxs-lookup"><span data-stu-id="19257-179">Exchange Server 2010</span></span>](https://docs.microsoft.com/office365/enterprise/exchange-2010-end-of-support)
- [<span data-ttu-id="19257-180">SharePoint Server 2010</span><span class="sxs-lookup"><span data-stu-id="19257-180">SharePoint Server 2010</span></span>](https://docs.microsoft.com/office365/enterprise/upgrade-from-sharepoint-2010)

<span data-ttu-id="19257-181">Office 2010 릴리스의 서버 제품을 Office 2013 또는 Office 2016 릴리스의 서버 제품으로 업그레이드하는 대신, 다음을 수행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="19257-181">Rather than upgrading these server products in the Office 2010 release with server products in the Office 2013 or Office 2016 release, consider:</span></span>

1. <span data-ttu-id="19257-182">Office 2010 서버의 데이터 Microsoft 365로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="19257-182">Migrating the data on your Office 2010 servers to Microsoft 365.</span></span> <span data-ttu-id="19257-183">이에 대한 도움이 필요하면 [Microsoft 365의 FastTrack](https://fasttrack.microsoft.com/microsoft365) 또는 Microsoft 파트너 고용을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="19257-183">To help with this, see [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365) or hire a Microsoft partner.</span></span>
2. <span data-ttu-id="19257-184">사용자에게 새 기능 및 작업 프로세스 롤아웃</span><span class="sxs-lookup"><span data-stu-id="19257-184">Rolling out the new functionality and work processes to your users.</span></span>
3. <span data-ttu-id="19257-185">Office 2010 서버 제품을 실행하는 온-프레미스 서버가 더 이상 필요하지 않은 경우 서비스 해제</span><span class="sxs-lookup"><span data-stu-id="19257-185">When there is no longer a need for the on-premises servers running Office 2010 server products, decommissioning them.</span></span>

### <a name="office-server-2013"></a><span data-ttu-id="19257-186">Office Server 2013</span><span class="sxs-lookup"><span data-stu-id="19257-186">Office Server 2013</span></span>

<span data-ttu-id="19257-p117">Office 2013 릴리스 서버 제품의 경우, 지원 종료가 결정되지 않았습니다. Office 2013 릴리스의 서버 제품을 Office 2016 릴리스의 서버 제품으로 업그레이드하는 대신, 다음을 수행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="19257-p117">For server products in the Office 2013 release, the end of support has not been determined. Rather than upgrading your server products in the Office 2013 release with server products in the Office 2016 release, consider:</span></span>

1. <span data-ttu-id="19257-p118">Office 2013 서버의 데이터를 Office 365로 마이그레이션. 이를 지원하기 위해 [Microsoft 365에 대한 FastTrack](https://fasttrack.microsoft.com/microsoft365)을 참조하거나 Microsoft 파트너를 고용하세요.</span><span class="sxs-lookup"><span data-stu-id="19257-p118">Migrating the data on your Office 2013 servers to Office 365. To help with this, see [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365) or hire a Microsoft partner.</span></span>
2. <span data-ttu-id="19257-191">사용자에게 새 기능 및 작업 프로세스 롤아웃</span><span class="sxs-lookup"><span data-stu-id="19257-191">Rolling out the new functionality and work processes to your users.</span></span>
3. <span data-ttu-id="19257-192">Office 2013 서버 제품을 실행하는 온-프레미스 서버가 더 이상 필요하지 않은 경우 서비스 해제</span><span class="sxs-lookup"><span data-stu-id="19257-192">When there is no longer a need for the on-premises servers running Office 2013 server products, decommissioning them.</span></span>

### <a name="office-server-2016"></a><span data-ttu-id="19257-193">Office Server 2016</span><span class="sxs-lookup"><span data-stu-id="19257-193">Office Server 2016</span></span>

<span data-ttu-id="19257-p119">Office 2016 릴리스 서버 제품의 경우, 지원 종료가 결정되지 않았습니다. 클라우드 기반 서비스 및 개선 기능을 활용하여 비즈니스의 디지털 혁신을 진행하려면 다음을 수행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="19257-p119">For server products in the Office 2016 release, the end of support has not been determined. To take advantage of the cloud-based service and enhancements to digitally transform your business, consider:</span></span>

1. <span data-ttu-id="19257-p120">Office 2016 서버의 데이터를 Office 365로 마이그레이션. 이를 지원하기 위해 [Microsoft 365에 대한 FastTrack](https://fasttrack.microsoft.com/microsoft365)을 참조하거나 Microsoft 파트너를 고용하세요.</span><span class="sxs-lookup"><span data-stu-id="19257-p120">Migrating the data on your Office 2016 servers to Office 365. To help with this, see [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365) or hire a Microsoft partner.</span></span>
2. <span data-ttu-id="19257-198">사용자에게 새 기능 및 작업 프로세스 롤아웃</span><span class="sxs-lookup"><span data-stu-id="19257-198">Rolling out the new functionality and work processes to your users.</span></span>
3. <span data-ttu-id="19257-199">Office 2016 서버 제품을 실행하는 온-프레미스 서버가 더 이상 필요하지 않은 경우 서비스 해제</span><span class="sxs-lookup"><span data-stu-id="19257-199">When there is no longer a need for the on-premises servers running Office 2016 server products, decommissioning them.</span></span>

## <a name="migration-for-microsoft-windows-7-and-81"></a><span data-ttu-id="19257-200">Microsoft Windows 7 및 8.1에 대한 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="19257-200">Migration for Microsoft Windows 7 and 8.1</span></span>

<span data-ttu-id="19257-201">Windows 7은 **2020년 1월 14일**에 지원이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="19257-201">Windows 7 reaches end of support on **January 14, 2020**.</span></span> <span data-ttu-id="19257-202">Windows 7 또는 Windows 8.1이 실행 중인 장치를 마이그레이션하려면 [현재 위치 업그레이드](https://docs.microsoft.com/microsoft-365/enterprise/windows10-deploy-inplaceupgrade)를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19257-202">To migrate your devices running Windows 7 or Windows 8.1, you can perform an [in-place upgrade](https://docs.microsoft.com/microsoft-365/enterprise/windows10-deploy-inplaceupgrade).</span></span> 

<span data-ttu-id="19257-203">추가 방법에 대해서는 [Windows 10 배포 시나리오](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="19257-203">For additional methods, see [Windows 10 deployment scenarios](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios).</span></span> <span data-ttu-id="19257-204">직접 [Windows 10 배포를 계획](https://aka.ms/planforwin10deployment)할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19257-204">You can also [plan for Windows 10 deployment](https://aka.ms/planforwin10deployment) on your own.</span></span>

## <a name="summary-of-options-for-office-2010-clients-and-servers-and-windows-7"></a><span data-ttu-id="19257-205">Office 2010 클라이언트 및 서버와 Windows 7에 대한 옵션 요약</span><span class="sxs-lookup"><span data-stu-id="19257-205">Summary of options for Office 2010 clients and servers and Windows 7</span></span>

<span data-ttu-id="19257-206">이러한 제품에 대한 업그레이드, 클라우드로 이동 옵션을 알기 쉽게 요약한 내용을 보려면 [지원 종료 포스터](../media/migration-microsoft-365-enterprise-workload/Office2010Windows7EndOfSupport.pdf)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="19257-206">For a visual summary of the upgrade, migrate, and move-to-the-cloud options for these products, see the [end of support poster](../media/migration-microsoft-365-enterprise-workload/Office2010Windows7EndOfSupport.pdf).</span></span>

<span data-ttu-id="19257-207">[![Office 2010 클라이언트 및 서버와 Windows 7에 대한 지원 종료 포스터 이미지](../media/migration-microsoft-365-enterprise-workload/office2010-windows7-end-of-support.png)](../media/migration-microsoft-365-enterprise-workload/Office2010Windows7EndOfSupport.pdf)</span><span class="sxs-lookup"><span data-stu-id="19257-207">[![Image for the end of support for Office 2010 clients and servers and Windows 7 poster](../media/migration-microsoft-365-enterprise-workload/office2010-windows7-end-of-support.png)](../media/migration-microsoft-365-enterprise-workload/Office2010Windows7EndOfSupport.pdf)</span></span>

<span data-ttu-id="19257-208">Microsoft 365 Enterprise에서 기본적으로 사용되는 경로와 결과 목적지 지원이 강조된 이 한 페이지짜리 포스터를 사용하여 Office 2010 클라이언트 및 서버 제품과 Windows 7의 지원 종료를 방지하는 다양한 방법을 빠르게 파악합니다.</span><span class="sxs-lookup"><span data-stu-id="19257-208">This one-page poster is a quick way to understand the various paths you can take to prevent Office 2010 client and server products and Windows 7 from reaching end of support, with preferred paths and resulting destination support in Microsoft 365 Enterprise highlighted.</span></span>

<span data-ttu-id="19257-209">[이 포스터를 다운로드](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/migration-microsoft-365-enterprise-workload/Office2010Windows7EndOfSupport.pdf)하고 편지형, 법률형 또는 타블로이드(11 x 17) 형식으로 인쇄할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19257-209">You can [download this poster](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/migration-microsoft-365-enterprise-workload/Office2010Windows7EndOfSupport.pdf) and print it in letter, legal, or tabloid (11 x 17) formats.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="19257-210">Microsoft에서 Microsoft 365 Enterprise를 수행하는 방법</span><span class="sxs-lookup"><span data-stu-id="19257-210">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="19257-211">다음 리소스를 사용하여 Microsoft의 IT 전문가가 회사를 Microsoft 365 Enterprise로 마이그레이션한 방법을 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="19257-211">See how IT experts at Microsoft migrated the company to Microsoft 365 Enterprise with these resources:</span></span> 

- [<span data-ttu-id="19257-212">Microsoft Office 365 ProPlus 배포 및 업데이트</span><span class="sxs-lookup"><span data-stu-id="19257-212">Deploying and updating Microsoft Office 365 ProPlus</span></span>](https://www.microsoft.com/itshowcase/Article/Content/757/Deploying-and-updating-Microsoft-Office-365-ProPlus)
- [<span data-ttu-id="19257-213">Microsoft에서 150,000개의 사서함을 Exchange Online으로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="19257-213">Microsoft migrates 150,000 mailboxes to Exchange Online</span></span>](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [<span data-ttu-id="19257-214">SharePoint를 클라우드로: Microsoft가 자체 마이그레이션을 수행한 방법 알아보기</span><span class="sxs-lookup"><span data-stu-id="19257-214">SharePoint to the cloud: Learn how Microsoft ran its own migration</span></span>](https://www.microsoft.com/itshowcase/Article/Content/691/SharePoint-to-the-cloud-Learn-how-Microsoft-ran-its-own-migration)
- [<span data-ttu-id="19257-215">Microsoft의 Windows 10dmf 현재 위치 업그레이드 방식으로 배포</span><span class="sxs-lookup"><span data-stu-id="19257-215">Deploying Windows 10 at Microsoft as an in-place upgrade</span></span>](https://www.microsoft.com/itshowcase/Article/Content/668/Deploying-Windows-10-at-Microsoft-as-an-inplace-upgrade)
- <span data-ttu-id="19257-216">[Windows 10 배포: Microsoft IT의 팀과 트릭](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT)(비디오)</span><span class="sxs-lookup"><span data-stu-id="19257-216">[Windows 10 deployment: tips and tricks from Microsoft IT](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT) (video)</span></span>

## <a name="transition-your-entire-organization"></a><span data-ttu-id="19257-217">전체 조직 전환</span><span class="sxs-lookup"><span data-stu-id="19257-217">Transition your entire organization</span></span>

<span data-ttu-id="19257-218">전체 조직을 Microsoft 365 Enterprise의 제품 및 서비스로 전환하는 방법을 더 잘 이해하려면 [전환 포스터](../media/deploy-microsoft-365-enterprise/transition-org-to-m365.pdf)를 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="19257-218">To get a better picture of how to move your entire organization to the products and services in Microsoft 365 Enterprise, download the [transition poster](../media/deploy-microsoft-365-enterprise/transition-org-to-m365.pdf).</span></span>

<span data-ttu-id="19257-219">[![Microsoft 365로 전환 포스터 이미지](../media/deploy-microsoft-365-enterprise/transition-org-to-m365.png)](../media/deploy-microsoft-365-enterprise/transition-org-to-m365.pdf)</span><span class="sxs-lookup"><span data-stu-id="19257-219">[![Image for the Transition to Microsoft 365 poster](../media/deploy-microsoft-365-enterprise/transition-org-to-m365.png)](../media/deploy-microsoft-365-enterprise/transition-org-to-m365.pdf)</span></span>

<span data-ttu-id="19257-220">이 두 페이지 포스터는 신속하게 기존 인프라를 인벤터리하여 Microsoft 365 Enterprise에서 해당 제품이나 서비스로 전환하는 방법에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="19257-220">This two-page poster is a quick way to inventory your existing infrastructure and get to the guidance for moving to the corresponding product or service in Microsoft 365 Enterprise.</span></span> <span data-ttu-id="19257-221">여기에는 Windows와 Office 제품, 장치 관리, ID, 정보 및 위협 방지와 같은 기타 인프라 및 보안 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="19257-221">It includes Windows and Office products and other infrastructure and security elements such as device management, identity, and information and threat protection.</span></span>

<span data-ttu-id="19257-222">[이 포스터를 다운로드](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/deploy-microsoft-365-enterprise/transition-org-to-m365.pdf)하고 편지형, 법률형 또는 타블로이드(11 x 17) 형식으로 인쇄할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19257-222">You can [download this poster](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/deploy-microsoft-365-enterprise/transition-org-to-m365.pdf) and print it in letter, legal, or tabloid (11 x 17) formats.</span></span>

## <a name="result"></a><span data-ttu-id="19257-223">결과</span><span class="sxs-lookup"><span data-stu-id="19257-223">Result</span></span>

<span data-ttu-id="19257-224">조직에 있는 이전 버전의 Microsoft Office, Office 서버 및 Windows가 Microsoft 365 Enterprise 버전으로 마이그레이션되었습니다.</span><span class="sxs-lookup"><span data-stu-id="19257-224">Your organization has migrated older versions of Microsoft Office, Office servers, and Windows to Microsoft 365 Enterprise.</span></span>
