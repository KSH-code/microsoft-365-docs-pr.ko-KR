---
title: Microsoft 365 Enterprise 배포
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 11/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 조직에서 Microsoft 365 Enterprise 배포하는 데 사용할 수 있는 리소스를 파악 합니다.
ms.openlocfilehash: ba0dd4d8af9f647b5368fdaa55837d3fe482fb55
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870257"
---
# <a name="deploy-microsoft-365-enterprise"></a><span data-ttu-id="07202-103">Microsoft 365 Enterprise 배포</span><span class="sxs-lookup"><span data-stu-id="07202-103">Deploy Microsoft 365 Enterprise</span></span>

<span data-ttu-id="07202-104">Microsoft 365 Enterprise는 Office 365, EMS(Enterprise Mobility + Security) 및 Windows 10 Enterprise가 통합된 제품으로, 다음과 같은 이점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="07202-104">Microsoft 365 Enterprise is a combination of Office 365, Enterprise Mobility + Security (EMS), and Windows 10 Enterprise that:</span></span> 

- <span data-ttu-id="07202-105">지능형 보안 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07202-105">Has intelligent security.</span></span>
- <span data-ttu-id="07202-106">간소화하도록 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="07202-106">Is integrated for simplicity.</span></span>
- <span data-ttu-id="07202-107">독창성을 촉진합니다.</span><span class="sxs-lookup"><span data-stu-id="07202-107">Unlocks creativity.</span></span>
- <span data-ttu-id="07202-108">팀 작업에 적합하게 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="07202-108">Is built for teamwork.</span></span>

<span data-ttu-id="07202-p101">이러한 이점은 세 가지 제품에 대한 라이선스를 획득하는 것만으로 실현되는 것이 아니라 제품과 해당 기능을 특정한 방식으로 배포해야 실현됩니다. 이 설명서 집합에서는 이러한 제품과 해당 기능의 배포 및 올바른 필수 구성을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="07202-p101">These benefits are not realized just by obtaining the licenses for these three products, but by deploying them and their features in a specific way. This documentation set guides you through that deployment and the correct and required configuration of these products and their features.</span></span>

<span data-ttu-id="07202-111">Microsoft 365 Enterprise를 배포하는 두 가지 주요 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07202-111">There are two main phases to deploying Microsoft 365 Enterprise:</span></span>

1. <span data-ttu-id="07202-112">먼저, 간소화된 관리를 위해 기본 제공 보안 및 통합용 필수 [기본 인프라](deploy-foundation-infrastructure.md)를 배포합니다. 그러면 향상된 최신 생산성 및 보안 기능으로 클라이언트 소프트웨어를 보다 쉽게 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07202-112">First, deploy the required [foundation infrastructure](deploy-foundation-infrastructure.md) for built-in security and integration for simplified management, which makes it easier to ensure your client software is updated with the latest productivity and security enhancements.</span></span>
2. <span data-ttu-id="07202-113">다음으로, 기본 인프라 위에 선택적 [워크로드 및 시나리오](deploy-workloads.md) 집합을 배포하여 조직에서 독창성 및 팀 작업을 촉진합니다.</span><span class="sxs-lookup"><span data-stu-id="07202-113">Next, deploy a set of optional [workloads and scenarios](deploy-workloads.md) on top of the foundation infrastructure, to unlock creativity and teamwork in your organization.</span></span>

<span data-ttu-id="07202-114">다음 그림에서는 기본 인프라와 워크로드 및 시나리오 간의 관계 및 콘텐츠 경로를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="07202-114">The following figure shows the relationship between the foundation infrastructure and the workloads and scenarios and your path through the content.</span></span>

![](./media/deploy-microsoft-365-enterprise/m365-deploy-content-arch.png)

<span data-ttu-id="07202-115">보안은 기본 인프라의 모든 단계에 기본적으로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="07202-115">Security is built into all phases of the foundation infrastructure.</span></span>

## <a name="fasttrack"></a><span data-ttu-id="07202-116">FastTrack</span><span class="sxs-lookup"><span data-stu-id="07202-116">FastTrack</span></span>

<span data-ttu-id="07202-p102">FastTrack은 사용자가 원하는 일정에 따라 클라우드로 전환할 수 있도록 Microsoft 엔지니어가 제공하는 지속적이고 반복 가능한 혜택입니다(구독의 일부로 제공). 또한 FastTrack은 필요에 따라 적격 파트너에게 추가 서비스에 대한 액세스를 제공합니다. 지금까지 40,000여 명의 고객을 보유한 FastTrack은 조직 전체에서 ROI를 극대화하고, 배포를 가속화하고, 도입을 늘리도록 도와줍니다. [Microsoft 365용 FastTrack](https://fasttrack.microsoft.com/microsoft365)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="07202-p102">FastTrack is an ongoing and repeatable benefit—available as part of your subscription—that is delivered by Microsoft engineers to help you move to the cloud at your own pace. FastTrack also gives you access to qualified partners for additional services, as needed. With over 40,000 customers enabled to date, FastTrack helps maximize ROI, accelerate deployment, and increase adoption across your organization. See [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365).</span></span>

<span data-ttu-id="07202-p103">FastTrack을 활용하여 Microsoft 365 Enterprise를 배포하려는 경우 [Microsoft 365 배포 관리자](https://aka.ms/microsoft365setupguide)를 사용하여 기본 인프라 배포 및 설정 방법에 대한 지침을 확인할 수 있습니다. 이 페이지에 액세스하려면 Office 365 또는 Microsoft 365 테넌트에서 전역 관리자로 로그온해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07202-p103">If you want to take advantage of FastTrack to deploy Microsoft 365 Enterprise, you can use the FastTrack [Microsoft 365 deployment advisor](https://aka.ms/microsoft365setupguide) for guidance on how to deploy and set up your foundation infrastructure. You must be signed on as a global administrator in an Office 365 or Microsoft 365 tenant in order to access this page.</span></span>

## <a name="take-a-test-drive"></a><span data-ttu-id="07202-123">시험 사용 수행</span><span class="sxs-lookup"><span data-stu-id="07202-123">Take a test drive</span></span>

<span data-ttu-id="07202-p104">프로덕션 배포 또는 특정 옵션의 배포 이전에 TLG(테스트 랩 가이드)를 사용하여 Microsoft 365 Enterprise의 여러 기능을 사용해 보세요. TLG는 평가판 또는 유료 구독을 사용하여 단순하지만 대표적인 환경에서 기능 또는 인프라의 구성을 안내하는 모듈식 규범 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="07202-p104">Play with Microsoft 365 Enterprise prior to production deployment or the deployment of specific options with Test Lab Guides (TLGs). TLGs are modular, prescriptive articles that step you through the configuration of infrastructure or a feature in a simplified but representative environment using trial or paid subscriptions.</span></span> 

<span data-ttu-id="07202-126">TLG를 사용하면 복잡한 구성, 작업 또는 종단 간 시나리오의 개념 증명을 보여주거나 사용자 지정하거나 구축할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07202-126">With TLGs, you can demonstrate, customize, or build a proof of concept of a complex configuration, workload, or end-to-end scenario.</span></span>

<span data-ttu-id="07202-127">자세한 내용은 [Microsoft 365 Enterprise 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="07202-127">For more information, see [Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>

![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

## <a name="how-customers-use-microsoft-365-enterprise"></a><span data-ttu-id="07202-129">고객이 Microsoft 365 Enterprise를 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="07202-129">How customers use Microsoft 365 Enterprise</span></span>

<span data-ttu-id="07202-130">고객이 Microsoft 365 Enterprise을 모든 사람이 창의적이면서 안전하게 작업하도록 지원하는 완전한 지능형 솔루션으로 사용하는 방법을 알아보려면 다음 리소스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="07202-130">See these resources to learn how customers are using Microsoft 365 Enterprise as their complete, intelligent solution that empowers everyone to be creative and work together securely:</span></span>

- <span data-ttu-id="07202-131">상태 서비스</span><span class="sxs-lookup"><span data-stu-id="07202-131">Health services</span></span>
  - [<span data-ttu-id="07202-132">Lilly는 내부 및 외부 협력으로 혁신을 가능하게 하고 신약의 출시 기간을 단축하는 데 도움이 되는 작업장을 구상함</span><span class="sxs-lookup"><span data-stu-id="07202-132">Lilly envisions a workplace where internal and external collaboration help enable innovation and accelerate time-to-market for new medicines</span></span>](https://aka.ms/Eli_CLS)
  - [<span data-ttu-id="07202-133">Healthcare Technology 혁신 담당자는 클라우드에서 당뇨병 예방을 가속화함</span><span class="sxs-lookup"><span data-stu-id="07202-133">Healthcare technology innovator accelerates diabetes prevention in the cloud </span></span>](https://aka.ms/Soleracasestudy)
  - [<span data-ttu-id="07202-134">Adventist Health System은 Microsoft 365를 사용하여 의료 서비스 전달을 개선함</span><span class="sxs-lookup"><span data-stu-id="07202-134">Adventist Health System is enhancing healthcare delivery using Microsoft 365</span></span>](https://aka.ms/adventisthealth)
  - [<span data-ttu-id="07202-135">Abrona에서는 Microsoft 365를 사용하여 GDPR 규정 준수를 가속화하고 생산성을 높임</span><span class="sxs-lookup"><span data-stu-id="07202-135">Abrona accelerates GDPR compliance and increases productivity with Microsoft 365</span></span>](https://aka.ms/Abrona)
  - [<span data-ttu-id="07202-136">Centra는 Microsoft 365 지능형 비즈니스 도구로 혁신을 진행하고, 환자 관리를 향상함</span><span class="sxs-lookup"><span data-stu-id="07202-136">Centra embraces transformation, improves patient care with Microsoft 365 intelligent business tools</span></span>](https://aka.ms/Centra_Health)
  - [<span data-ttu-id="07202-137">Advocate Aurora Health는 공동 작업을 향상하는 Microsoft 의료 서비스 조정 솔루션을 사용하여 환자의 건강을 도움</span><span class="sxs-lookup"><span data-stu-id="07202-137">Advocate Aurora Health helps patients live well using Microsoft care coordination solution to enhance collaboration</span></span>](https://aka.ms/Advocate_)
- <span data-ttu-id="07202-138">금융 서비스</span><span class="sxs-lookup"><span data-stu-id="07202-138">Financial services</span></span>
  - [<span data-ttu-id="07202-139">TD Bank는 Office 365 및 Windows 10의 지원 기술로 직원 업무를 지원함</span><span class="sxs-lookup"><span data-stu-id="07202-139">TD Bank empowers employees with assistive technology in Office 365 and Windows 10</span></span>](https://aka.ms/tdbankgroup)
  - [<span data-ttu-id="07202-140">가족 수당 신고 처리 업체에서 비즈니스 성장에 도움을 주는 통합형 솔루션 선택</span><span class="sxs-lookup"><span data-stu-id="07202-140">Family tax preparation startup chooses all-in-one solution to help grow business</span></span>](https://aka.ms/SOSCaseStudy)
- <span data-ttu-id="07202-141">교통</span><span class="sxs-lookup"><span data-stu-id="07202-141">Transportation</span></span>
  - [<span data-ttu-id="07202-142">Qantas에서는 직원들이 Microsoft 365를 통해 최상의 업무를 수행할 수 있도록 지원하여 고객 경험을 향상함</span><span class="sxs-lookup"><span data-stu-id="07202-142">Qantas empowers employees to do their best work with Microsoft 365, enhancing customer experience</span></span>](https://aka.ms/Qantas_CS)
  - [<span data-ttu-id="07202-143">Amtrak에서는 Microsoft 365를 사용하여 모바일 엔터프라이즈를 일정보다 먼저 운영함</span><span class="sxs-lookup"><span data-stu-id="07202-143">Amtrak keeps its mobile enterprise running ahead of schedule with Microsoft 365</span></span>](https://aka.ms/Amtrak_)
- <span data-ttu-id="07202-144">제조</span><span class="sxs-lookup"><span data-stu-id="07202-144">Manufacturing</span></span>
  - [<span data-ttu-id="07202-145">철강 기업은 클라우드에서 하드웨어 비용을 없애고, IT를 간소화하고, 모바일 생산성을 확보함</span><span class="sxs-lookup"><span data-stu-id="07202-145">Steel company eliminates hardware costs, streamlines IT, and gains mobile productivity in the cloud</span></span>](https://aka.ms/Steeledalecasestudy)
  - [<span data-ttu-id="07202-146">자수 장비 공급업체가 클라우드 기반 서비스로 비즈니스를 강화하고, 다른 중소기업으로 인지도를 넓힘</span><span class="sxs-lookup"><span data-stu-id="07202-146">Embroidery equipment supplier empowers its business with cloud-based services, spreads word to other small businesses</span></span>](https://aka.ms/PriorityLLCCaseStudy)
  - [<span data-ttu-id="07202-147">이 아버지와 아들의 사업은 장애가 있는 직원도 업무 목표에 달성할 수 있다는 것을 보여줌</span><span class="sxs-lookup"><span data-stu-id="07202-147">Father and son business shows the world what employees with disabilities can achieve</span></span>](https://aka.ms/JCSCaseStudy)
  - [<span data-ttu-id="07202-148">이 코코넛 회사는 공동 작업 도구를 현대화하여 이동성, 메트릭 및 생산성이 향상됨</span><span class="sxs-lookup"><span data-stu-id="07202-148">Coconut company gains improved mobility, better metrics, and increased productivity by modernizing collaboration tools</span></span>](https://aka.ms/SilvermillCS)
  - [<span data-ttu-id="07202-149">Microsoft 365 Business로 미래를 보장하는 유연성과 향상된 보안을 제공받는 일본의 번창하는 혁신 업체</span><span class="sxs-lookup"><span data-stu-id="07202-149">Thriving Japanese innovator finds future-proof flexibility and enhanced security with Microsoft 365 Business</span></span>](https://aka.ms/DreamFactoryCaseStudy)
- <span data-ttu-id="07202-150">엔지니어링</span><span class="sxs-lookup"><span data-stu-id="07202-150">Engineering</span></span>
   - [<span data-ttu-id="07202-151">케이던스를 통해 모바일 공동 작업 도구의 속도 높이기</span><span class="sxs-lookup"><span data-stu-id="07202-151">Cadence increases the pace of business with mobile collaboration tools</span></span>](https://customers.microsoft.com/story/cadence-partner-professional-services-microsoft-365)
- <span data-ttu-id="07202-152">전문 서비스</span><span class="sxs-lookup"><span data-stu-id="07202-152">Professional services</span></span>
  - [<span data-ttu-id="07202-153">부티크 기업 및 부동산 법률 회사에서 포괄적인 클라우드 기반 플랫폼으로 확장을 지원함</span><span class="sxs-lookup"><span data-stu-id="07202-153">Boutique business and real estate law firm supports expansion with comprehensive cloud-based platform </span></span>](https://aka.ms/Lieserskaffcasestudy)
  - [<span data-ttu-id="07202-154">스포츠 기술 회사에서 바이오 피드백 및 분석을 통해 운동 선수들이 최고 기량에 도달하도록 지원함</span><span class="sxs-lookup"><span data-stu-id="07202-154">Sports technology company helps athletes reach their peak through biofeedback and analytics </span></span>](https://aka.ms/KMOTIONCasestudy)
  - [<span data-ttu-id="07202-155">디지털 혁신 및 클라우드로 비즈니스 협회가 회원을 덜 잘 관리하도록 지원</span><span class="sxs-lookup"><span data-stu-id="07202-155">Digital transformation and the cloud empower business association to serve its members better </span></span>](https://aka.ms/AIMCS)
- <span data-ttu-id="07202-156">에너지 서비스</span><span class="sxs-lookup"><span data-stu-id="07202-156">Energy services</span></span>
  - [<span data-ttu-id="07202-157">Schlumberger에서 Microsoft 365로 글로벌 팀 작업을 보다 구체적으로 조정함</span><span class="sxs-lookup"><span data-stu-id="07202-157">Schlumberger refines global teamwork with Microsoft 365</span></span>](https://aka.ms/Schlumberger_)
- <span data-ttu-id="07202-158">건설</span><span class="sxs-lookup"><span data-stu-id="07202-158">Construction</span></span>
  - [<span data-ttu-id="07202-159">일반 건설 계약업체에서 데이터 검색 보안 솔루션을 통해 Microsoft 365의 공동 작업 기능 활용</span><span class="sxs-lookup"><span data-stu-id="07202-159">Search for data security solution unearths collaborative capabilities of Microsoft 365 at general contracting company</span></span>](https://aka.ms/Transbluecasestudy)
- <span data-ttu-id="07202-160">컨설팅</span><span class="sxs-lookup"><span data-stu-id="07202-160">Consulting</span></span>
  - [<span data-ttu-id="07202-161">ERM은 Microsoft 365를 사용하여 지속 가능한 미래에 기여</span><span class="sxs-lookup"><span data-stu-id="07202-161">ERM contributes to a more sustainable future with Microsoft 365</span></span>](https://aka.ms/ERM_CS)
- <span data-ttu-id="07202-162">비영리</span><span class="sxs-lookup"><span data-stu-id="07202-162">Non-profit</span></span>
  - [<span data-ttu-id="07202-163">비영리 단체에서 클라우드로 이동하여 보안, 이동성 및 공동 작업을 향상하면서 50만 달러를 절약함</span><span class="sxs-lookup"><span data-stu-id="07202-163">Move to the cloud saves nonprofit $500,000 while improving security, mobility, and collaboration </span></span>](https://aka.ms/MOWCaseStudy)
  
## <a name="how-microsoft-uses-microsoft-365-enterprise"></a><span data-ttu-id="07202-164">Microsoft에서 Microsoft 365 Enterprise를 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="07202-164">How Microsoft uses Microsoft 365 Enterprise</span></span>

<span data-ttu-id="07202-165">Microsoft IT 부서의 내부를 살펴보고 Microsoft 365 Enterprise가 배포된 방식과 Microsoft 직원들이 이 플랫폼을 매일 사용하는 방식을 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="07202-165">Take a peek inside Microsoft IT and learn how they deployed Microsoft 365 Enterprise and how Microsoft employees use it every day.</span></span>

### <a name="networking"></a><span data-ttu-id="07202-166">네트워킹</span><span class="sxs-lookup"><span data-stu-id="07202-166">Networking</span></span>

- [<span data-ttu-id="07202-167">Microsoft Office 365의 네트워크 성능 최적화</span><span class="sxs-lookup"><span data-stu-id="07202-167">Optimizing network performance for Microsoft Office 365</span></span>](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365)

### <a name="identity"></a><span data-ttu-id="07202-168">ID</span><span class="sxs-lookup"><span data-stu-id="07202-168">Identity</span></span>

- [<span data-ttu-id="07202-169">Microsoft에서 사용자 ID 및 보안 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="07202-169">Managing user identities and secure access at Microsoft</span></span>](https://www.microsoft.com/itshowcase/Article/Content/931/Managing-user-identities-and-secure-access-at-Microsoft)
- [<span data-ttu-id="07202-170">상승된 액세스 권한에 대해 Azure AD Privileged Identity Management 사용</span><span class="sxs-lookup"><span data-stu-id="07202-170">Using Azure AD Privileged Identity Management for elevated access</span></span>](https://www.microsoft.com/itshowcase/Article/Content/887/Using-Azure-AD-Privileged-Identity-Management-for-elevated-access)

### <a name="windows-10-enterprise"></a><span data-ttu-id="07202-171">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="07202-171">Windows 10 Enterprise</span></span>

- [<span data-ttu-id="07202-172">조직의 원활한 Windows 10 배포 준비</span><span class="sxs-lookup"><span data-stu-id="07202-172">Preparing your organization for a seamless Windows 10 deployment</span></span>](https://www.microsoft.com/itshowcase/windows10deployment?wt.mc_id=bmkg_itsc)
- [<span data-ttu-id="07202-173">Microsoft에서 Windows를 서비스로 채택</span><span class="sxs-lookup"><span data-stu-id="07202-173">Adopting Windows as a service at Microsoft</span></span>](https://www.microsoft.com/itshowcase/Article/Content/851/Adopting-Windows-as-a-service-at-Microsoft)
- [<span data-ttu-id="07202-174">Microsoft의 Windows 10dmf 현재 위치 업그레이드 방식으로 배포</span><span class="sxs-lookup"><span data-stu-id="07202-174">Deploying Windows 10 at Microsoft as an in-place upgrade</span></span>](https://www.microsoft.com/itshowcase/Article/Content/668/Deploying-Windows-10-at-Microsoft-as-an-inplace-upgrade)
- [<span data-ttu-id="07202-175">비즈니스용 Windows Hello를 통해 강력한 사용자 인증 구현</span><span class="sxs-lookup"><span data-stu-id="07202-175">Implementing strong user authentication with Windows Hello for Business</span></span>](https://www.microsoft.com/itshowcase/Article/Content/756/Implementing-strong-user-authentication-with-Windows-Hello-for-Business)
- <span data-ttu-id="07202-176">[Windows 10 배포: Microsoft IT의 팀과 트릭](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT)(비디오)</span><span class="sxs-lookup"><span data-stu-id="07202-176">[Windows 10 deployment: tips and tricks from Microsoft IT](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT) (video)</span></span>
- [<span data-ttu-id="07202-177">Windows Defender ATP로 정교한 위협 감지 지원</span><span class="sxs-lookup"><span data-stu-id="07202-177">Windows Defender ATP helps detect sophisticated threats</span></span>](https://www.microsoft.com/itshowcase/Article/Content/854/Windows-Defender-ATP-helps-detect-sophisticated-threats)
- <span data-ttu-id="07202-178">[Windows Defender 및 Windows Defender ATP로 최신 엔터프라이즈 보안 유지](https://www.microsoft.com/itshowcase/Article/Content/903/Securing-the-modern-enterprise-with-Windows-Defender-and-Windows-Defender-ATP)(비디오)</span><span class="sxs-lookup"><span data-stu-id="07202-178">[Securing the modern enterprise with Windows Defender and Windows Defender ATP](https://www.microsoft.com/itshowcase/Article/Content/903/Securing-the-modern-enterprise-with-Windows-Defender-and-Windows-Defender-ATP) (video)</span></span>

### <a name="office-365-proplus"></a><span data-ttu-id="07202-179">Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="07202-179">Office 365 ProPlus</span></span>

- [<span data-ttu-id="07202-180">원활한 Office 365 ProPlus 2016 배포를 위해 조직 준비</span><span class="sxs-lookup"><span data-stu-id="07202-180">Preparing your organization for a seamless Office 365 ProPlus 2016 deployment</span></span>](https://www.microsoft.com/itshowcase/Office365adoption)
- [<span data-ttu-id="07202-181">Microsoft Office 365 ProPlus 배포 및 업데이트</span><span class="sxs-lookup"><span data-stu-id="07202-181">Deploying and updating Microsoft Office 365 ProPlus</span></span>](https://www.microsoft.com/itshowcase/Article/Content/757/Deploying-and-updating-Microsoft-Office-365-ProPlus)
- <span data-ttu-id="07202-182">[Microsoft Office 365 ProPlus를 배포하는 데 도움이 되는 자동화 및 업데이트 채널](https://www.microsoft.com/itshowcase/Article/Content/794/Automation-and-update-channels-help-deploy-Microsoft-Office-365-ProPlus)(비디오)</span><span class="sxs-lookup"><span data-stu-id="07202-182">[Automation and update channels help deploy Microsoft Office 365 ProPlus](https://www.microsoft.com/itshowcase/Article/Content/794/Automation-and-update-channels-help-deploy-Microsoft-Office-365-ProPlus) (video)</span></span>

### <a name="mobility-and-device-management"></a><span data-ttu-id="07202-183">이동성 및 장치 관리</span><span class="sxs-lookup"><span data-stu-id="07202-183">Mobility and device management</span></span>

- [<span data-ttu-id="07202-184">Enterprise Mobility + Security를 통한 최신 모바일 생산성 관리</span><span class="sxs-lookup"><span data-stu-id="07202-184">Managing modern mobile productivity with Enterprise Mobility + Security</span></span>](https://www.microsoft.com/itshowcase/Article/Content/972/Managing-modern-mobile-productivity-with-Enterprise-Mobility--Security)
- [<span data-ttu-id="07202-185">Microsoft Intune으로 Windows 10 장치에서 작동하도록 연결</span><span class="sxs-lookup"><span data-stu-id="07202-185">Connecting to work on your Windows 10 device with Microsoft Intune</span></span>](https://www.microsoft.com/itshowcase/Article/Content/783/Connecting-to-work-on-your-Windows-10-device-with-Microsoft-Intune)
- [<span data-ttu-id="07202-186">Microsoft에서 iOS, OS X 및 Android 장치의 모바일 생산성 사용</span><span class="sxs-lookup"><span data-stu-id="07202-186">Enabling mobile productivity for iOS, OS X, and Android devices at Microsoft</span></span>](https://www.microsoft.com/itshowcase/Article/Content/773/Enabling-mobile-productivity-for-iOS-OS-X-and-Android-devices-at-Microsoft)

### <a name="security-and-information-protection"></a><span data-ttu-id="07202-187">보안 및 정보 보호</span><span class="sxs-lookup"><span data-stu-id="07202-187">Security and information protection</span></span>

- [<span data-ttu-id="07202-188">Azure Information Protection을 사용하여 클라우드의 파일 보호</span><span class="sxs-lookup"><span data-stu-id="07202-188">Protecting files in the cloud with Azure Information Protection</span></span>](https://www.microsoft.com/itshowcase/Article/Content/924/Protecting-files-in-the-cloud-with-Azure-Information-Protection)
- [<span data-ttu-id="07202-189">Microsoft는 위협 인텔리전스를 사용하여 위협 방지, 감지 및 대응</span><span class="sxs-lookup"><span data-stu-id="07202-189">Microsoft uses threat intelligence to protect, detect, and respond to threats</span></span>](https://www.microsoft.com/itshowcase/Article/Content/934/Microsoft-uses-threat-intelligence-to-protect-detect-and-respond-to-threats)
- [<span data-ttu-id="07202-190">Microsoft는 Office 365를 사용하여 피싱 시도 저지</span><span class="sxs-lookup"><span data-stu-id="07202-190">Microsoft thwarts phishing attempts with Office 365</span></span>](https://www.microsoft.com/itshowcase/Article/Content/956/Microsoft-thwarts-phishing-attempts-with-Office-365)

### <a name="microsoft-teams"></a><span data-ttu-id="07202-191">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="07202-191">Microsoft Teams</span></span>

- [<span data-ttu-id="07202-192">Microsoft Teams 배포를 통한 공동 작업의 간소화 및 팀워크 개선</span><span class="sxs-lookup"><span data-stu-id="07202-192">Deploying Microsoft Teams streamlines collaboration and improves teamwork</span></span>](https://www.microsoft.com/itshowcase/Article/Content/1013/Deploying-Microsoft-Teams-streamlines-collaboration-and-improves-teamwork)
- [<span data-ttu-id="07202-193">Microsoft Teams를 통한 최신 Microsoft 작업 공간에서의 공동 작업 증가</span><span class="sxs-lookup"><span data-stu-id="07202-193">Microsoft Teams increases collaboration in the modern workplace at Microsoft</span></span>](https://www.microsoft.com/itshowcase/Article/Content/1012/Microsoft-Teams-increases-collaboration-in-the-modern-workplace-at-Microsoft)

### <a name="data-migration"></a><span data-ttu-id="07202-194">데이터 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="07202-194">Data migration</span></span>

- [<span data-ttu-id="07202-195">Microsoft에서 150,000개의 사서함을 Exchange Online으로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="07202-195">Microsoft migrates 150,000 mailboxes to Exchange Online</span></span>](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [<span data-ttu-id="07202-196">SharePoint를 클라우드로: Microsoft가 자체 마이그레이션을 수행한 방법 알아보기</span><span class="sxs-lookup"><span data-stu-id="07202-196">SharePoint to the cloud: Learn how Microsoft ran its own migration</span></span>](https://www.microsoft.com/itshowcase/Article/Content/691/SharePoint-to-the-cloud-Learn-how-Microsoft-ran-its-own-migration)

## <a name="how-the-contoso-corporation-deployed-microsoft-365-enterprise"></a><span data-ttu-id="07202-197">Contoso Corporation에서 Microsoft 365 Enterprise를 배포한 방식</span><span class="sxs-lookup"><span data-stu-id="07202-197">How the Contoso Corporation deployed Microsoft 365 Enterprise</span></span>

<span data-ttu-id="07202-p105">Contoso Corporation는 파리에 본사가 있는 가상의 대표적 글로벌 제조 대기업입니다. [Contoso가 Microsoft 365 Enterprise를 배포](contoso-case-study.md)하고 네트워킹, ID, Windows 10 Enterprise, Office 365 ProPlus, 모바일 장치 관리, 정보 보호 및 보안에 대한 중요 디자인 결정 및 구현 세부 사항을 진행하는 방식을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="07202-p105">The Contoso Corporation is a fictional but representative global manufacturing conglomerate with its headquarters in Paris. See how [Contoso deployed Microsoft 365 Enterprise](contoso-case-study.md) and addressed major design decisions and implementation details for networking, identity, Windows 10 Enterprise, Office 365 ProPlus, mobile device management, information protection, and security.</span></span> 

![](./media/contoso-overview/contoso-icon.png)

## <a name="additional-microsoft-365-solutions"></a><span data-ttu-id="07202-200">추가 Microsoft 365 솔루션</span><span class="sxs-lookup"><span data-stu-id="07202-200">Additional Microsoft 365 solutions</span></span>

- [<span data-ttu-id="07202-201">Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="07202-201">Microsoft 365 Business</span></span>](https://docs.microsoft.com/microsoft-365/business/)
 
  <span data-ttu-id="07202-202">Office 365의 동급 최고의 생산성 및 공동 작업 기능을 장치 관리 및 보안 솔루션과 결합하여 SMB(중소 중견 기업)의 비즈니스 데이터를 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="07202-202">Bring together the best-in-class productivity and collaboration capabilities of Office 365 with device management and security solutions to safeguard business data for small and midsize businesses (SMB).</span></span>

- [<span data-ttu-id="07202-203">Microsoft 365 Education</span><span class="sxs-lookup"><span data-stu-id="07202-203">Microsoft 365 Education</span></span>](https://docs.microsoft.com/education)
 
  <span data-ttu-id="07202-204">강사들이 교육용으로 디자인된 저렴한 단일 솔루션에서 독창성을 발휘하고, 팀 작업을 촉진하고, 간편하고 안전한 환경을 제공하도록 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="07202-204">Empower educators to unlock creativity, promote teamwork, and provide a simple and safe experience in a single, affordable solution built for education.</span></span>

## <a name="next-step"></a><span data-ttu-id="07202-205">다음 단계</span><span class="sxs-lookup"><span data-stu-id="07202-205">Next step</span></span>

<span data-ttu-id="07202-206">[FastTrack](https://fasttrack.microsoft.com/microsoft365)을 사용하거나 [기본 인프라](deploy-foundation-infrastructure.md)로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07202-206">Use [FastTrack](https://fasttrack.microsoft.com/microsoft365) or get started with the [foundation infrastructure](deploy-foundation-infrastructure.md).</span></span>
