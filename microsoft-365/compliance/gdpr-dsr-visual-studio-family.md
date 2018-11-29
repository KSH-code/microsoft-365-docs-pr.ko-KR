---
title: GDPR에 대한 Visual Studio 제품군 데이터 주체 요청
description: GDPR에 대한 Visual Studio 제품군 데이터 주체 요청
keywords: Visual Studio, Visual Studio Code, Mac용 Visual Studio, Visual Studio 설명서, 개인 정보, GDPR
localization_priority: Priority
audience: itpro
ms.prod: visual-studio
ms.topic: article
ms.date: 05/24/2018
author: PoulChapman
ms.author: pchapman
manager: scalla
ms.collection: GDPR
ms.workload:
- multiple
ms.openlocfilehash: 09bba28648cbee6dd32c2005bcb584e97a4c534e
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870042"
---
# <a name="visual-studio-family-data-subject-requests-for-the-gdpr"></a><span data-ttu-id="69f54-104">GDPR에 대한 Visual Studio 제품군 데이터 주체 요청</span><span class="sxs-lookup"><span data-stu-id="69f54-104">Visual Studio Family Data Subject Requests for the GDPR</span></span>

<span data-ttu-id="69f54-p101">EU [일반 데이터 보호 규정(GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm)은 사용자(규정에 _데이터 주체_로 알려짐)에게 개인 데이터를 관리할 수 있는 권리를 부여합니다. 개인 데이터는 GDPR에 따라 식별되거나 식별 가능한 자연인과 관련된 모든 데이터로 매우 광범위하게 정의됩니다. GDPR은 데이터 주체 특정 권한을 개인 데이터에 제공합니다. 이러한 권한에는 개인 데이터 복사본 획득, 수정 요청, 처리 제한, 삭제 또는 전자 형식으로 수신하는 권한이 포함됩니다. 해당 데이터 주체의 개인 데이터에 대해 조치를 취하는 데이터 컨트롤러(개인 데이터를 제어하는 고용주 또는 기타 유형의 에이전시 또는 조직)에 대한 데이터 주체의 공식 요청을 _데이터 주체 요청_ 또는 DSR이라고 합니다. GDPR에 대한 일반적인 정보는 [Service Trust Portal의 GDPR 섹션](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="69f54-p101">The European Union [General Data Protection Regulation (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) gives rights to people (known in the regulation as _data subjects_) to manage their personal data. Personal data is defined very broadly under the GDPR as any data that relates to an identified or identifiable natural person. The GDPR gives data subjects specific rights to their personal data; these rights include obtaining copies of personal data, requesting corrections to it, restricting the processing of it, deleting it, or receiving it in an electronic format. A formal request by a data subject to a data controller (an employer or other type of agency or organization that has control over personal data) to take an action on that data subject's personal data is called a _data subject request_ or DSR. For general information about GDPR, see the [GDPR section of the Service Trust portal](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted).</span></span>

## <a name="products-covered-by-this-guide"></a><span data-ttu-id="69f54-110">이 가이드 적용을 받는 제품</span><span class="sxs-lookup"><span data-stu-id="69f54-110">Products covered by this guide</span></span>

<span data-ttu-id="69f54-p102">이 가이드에서는 Microsoft 도구를 사용하여 Mac 및 Microsoft 확장용 Visual Studio 및 Virtual Studio의 인증된(로그인된) 세션 사용 동안 수집된 개인 데이터를 삭제하거나 해당 Studio와 Visual Studio Code에 내보냅니다. 또한 이 가이드는 Visual Studio 개발자 커뮤니티, NuGet.org 및 ASP.NET 웹 사이트를 사용할 때 수집되는 개인 데이터에 대한 데이터 주체 요청 방법을 설명합니다. 이러한 제품은 Microsoft 이외의 도구 및 확장을 사용할 수 있으며 Microsoft는 이러한 도구 및 확장을 위한 데이터 프로세서 또는 컨트롤러가 아닙니다. 사용자는 도구 또는 확장 공급자에 연락하여 이러한 도구 및 확장에 대한 개인 데이터와 컬렉션 정책을 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69f54-p102">This guide discusses how to use Microsoft tools to export or delete personal data collected during authenticated (signed-in) session usage of Visual Studio and Visual Studio for Mac and Microsoft extensions to them and to Visual Studio Code. This guide also covers how to make data subject requests for personal data collected when using Visual Studio Developer Community, NuGet.org, and the ASP.NET website. These products may enable use of non-Microsoft tools and extensions, and Microsoft is not a data processor or controller for these tools and extensions. Users should contact the tool or extension provider to understand the personal data and collection policies for these tools and extensions.</span></span>

## <a name="additional-privacy-information"></a><span data-ttu-id="69f54-115">추가 개인 정보 보호 정보</span><span class="sxs-lookup"><span data-stu-id="69f54-115">Additional privacy information</span></span>

<span data-ttu-id="69f54-116">제품과 함께 제공되는 Microsoft 소프트웨어 사용 조건, [Microsoft 개인정보취급방침](https://go.microsoft.com/fwlink/?LinkId=660726) 및 [Microsoft GDPR 약속](https://docs.microsoft.com/legal/gdpr)은 데이터 처리 규정을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="69f54-116">The Microsoft Software License Terms accompanying the products, the [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?LinkId=660726), and [Microsoft's GDPR Commitments](https://docs.microsoft.com/legal/gdpr) describe our data processing practices.</span></span>

## <a name="visual-studio-visual-studio-for-mac-and-visual-studio-code"></a><span data-ttu-id="69f54-117">Visual Studio, Mac용 Visual Studio, Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="69f54-117">Visual Studio, Visual Studio for Mac, and Visual Studio Code</span></span>

### <a name="personal-data-we-collect"></a><span data-ttu-id="69f54-118">수집한 개인 데이터</span><span class="sxs-lookup"><span data-stu-id="69f54-118">Personal data we collect</span></span>

<span data-ttu-id="69f54-p103">GDPR에 따른 데이터 프로세서로, Microsoft는 사용자가 Mac 및 Microsoft 확장용 Visual Studio 및 Visual Studio에 대한 경험을 제공하고 해당 Studio 및 Visual Studio Code를 향상하기 위해 필요한 데이터를 수집합니다. 데이터에는 고객 데이터와 시스템 생성 로그라는 두 가지 범주가 있습니다. 고객 데이터에는 이러한 제품이 제공하는 서비스를 수행하는 데 필요한 사용자 식별 가능한 트랜잭션 및 상호 작용 데이터가 포함됩니다. 예를 들어, 사용자에게 로밍 설정과 같은 개인화된 환경을 제공하려면 사용자 계정 정보 및 설정 데이터를 수집해야 합니다. 시스템 생성 로그는 문제를 식별하고 해결하며 제품과 서비스를 개선하는 데 사용되는 사용 또는 진단 데이터이며 사용자 이름과 같은 최종 사용자에 대한 식별 가능한 정보를 포함할 수 있습니다. 시스템 생성 로그는 18개월 동안 보관됩니다. 예를 들어, 시스템 생성 로그는 매일 제품 사용에 대해 집계되며 사용 날짜, 사용된 제품(예: "Visual Studio 2017"), 취한 조치(예: "vs/core/packagecostsummary/solutionload"), 조치가 취해진 횟수를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="69f54-p103">As a data processor under the GDPR, Microsoft collects the data we need from users to provide experiences for and improve Visual Studio and Visual Studio for Mac and Microsoft extensions to them and to Visual Studio Code. There are two categories of data: customer data and system-generated logs. Customer data includes user-identifiable transactional and interactional data that these products need to perform the service they provide. For example, to provide users with personalized experiences such as roaming settings, we need to collect user account information and settings data. System-generated logs are usage or diagnostic data that are used to help identify and troubleshoot problems and improve our products and services, and may also contain identifiable information about end users, such as a user name. System-generated logs are retained for no more than 18 months. As an example, system-generated logs are aggregated for each day of product usage and include the usage date, the product used (for example, "Visual Studio 2017"), the action you took (for example, "vs/core/packagecostsummary/solutionload"), and the number of times the action was taken, as shown in this sample:</span></span>

```
{Time":"2/23/2018 12:00:00 AM","AppName":"Visual Studio 2017","Action":"vs/core/packagecostsummary/solutionload","Target":"1 times",
"DevicePlatform":"Windows 10 Enterprise","IP":null,"InputMethod":null,
"SearchTerm":null,"SearchResult":null}

{Time":"2/23/2018 12:00:00 AM","AppName":"Visual Studio 2017","Action":"vs/ide/connected/accountmanagement/account","Target":"1 times",
"DevicePlatform": "Windows 10 Enterprise","IP":null,"InputMethod":null,
"SearchTerm":null,"SearchResult":null}

{"Time":"2/27/2018 12:00:00 AM","AppName":"Visual Studio 2017","Action":"vs/core/perf/satellitepagefileusage","Target":"23 times",
"DevicePlatform":"Windows 10 Enterprise","IP":null,"InputMethod":null,
"SearchTerm":null,"SearchResult":null}
```

<span data-ttu-id="69f54-126">자세한 내용은 [Visual Studio에서 수집된 시스템 생성 로그](https://docs.microsoft.com/visualstudio/ide/diagnostic-data-collection)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="69f54-126">For more information, see [System-generated logs collected by Visual Studio](https://docs.microsoft.com/visualstudio/ide/diagnostic-data-collection).</span></span>

<span data-ttu-id="69f54-p104">인증된 ID에 첨부된 개인 데이터만 DSR에서 처리할 수 있습니다. 예를 들어, Visual Studio Code는 로그인을 지원하지 않으므로 Visual Studio Code의 시스템 생성 로그를 인증된 ID에 첨부하지 않으면 처리할 수 없습니다. 하지만 Visual Studio Code에 대한 일부 Microsoft 확장은 인증된 데이터를 제공할 수 있으며 이 데이터는 DSR로 처리될 수 있습니다. 자세한 내용은 [GDPR 및 Visual Studio Code](https://code.visualstudio.com/docs/supporting/faq#_gdpr-and-vs-code)를 참조하세요. 일반적으로 Visual Studio 2013 이전 버전의 데이터는 저장하지 않습니다. 하지만 특정 확장 및 구성 요소는 인증된 ID에 첨부된 데이터를 제공할 수 있으며 아래에 설명된 대로 DSR에서 처리될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69f54-p104">Only personal data that is attached to authenticated identities can be serviced by a DSR. So, for example, because Visual Studio Code does not support sign-in, system-generated logs from it are not attached to an authenticated identity and cannot be serviced. However, some Microsoft extensions for Visual Studio Code may provide authenticated data, and this data can be serviced by a DSR. For more information, see [GDPR and Visual Studio Code](https://code.visualstudio.com/docs/supporting/faq#_gdpr-and-vs-code). In general, we do not store data for Visual Studio 2013 and earlier; however, certain extensions and components may provide data attached to authenticated identities and can be serviced by a DSR as outlined below.</span></span>

### <a name="how-users-can-control-personal-data"></a><span data-ttu-id="69f54-132">사용자가 개인 데이터를 제어하는 방법</span><span class="sxs-lookup"><span data-stu-id="69f54-132">How users can control personal data</span></span>

<span data-ttu-id="69f54-133">Visual Studio 2015 이상, Mac용 Visual Studio, Visual Studio Code는 사용자가 데이터 컬렉션을 중지하고 컨트롤러가 이미 수집한 데이터를 내보내거나 삭제할 수 있는 다음과 같은 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="69f54-133">Visual Studio 2015 and later, Visual Studio for Mac, and Visual Studio Code provide the following means for your users to stop data collection, and for you as controller to export, or delete data that has already been gathered.</span></span>

#### <a name="in-app-settings"></a><span data-ttu-id="69f54-134">앱 내 설정</span><span class="sxs-lookup"><span data-stu-id="69f54-134">In-app settings</span></span>

<span data-ttu-id="69f54-p105">사용자는 이러한 제품의 개인 정보 설정을 제어할 수 있습니다. 자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="69f54-p105">Users can control the privacy settings for these products. For more information, see the following</span></span>

- <span data-ttu-id="69f54-137">[Visual Studio에서 개인 정보 설정을 관리하는 방법입니다](https://docs.microsoft.com/visualstudio/ide/visual-studio-experience-improvement-program).</span><span class="sxs-lookup"><span data-stu-id="69f54-137">[How to manage privacy settings in Visual Studio](https://docs.microsoft.com/visualstudio/ide/visual-studio-experience-improvement-program).</span></span>
- <span data-ttu-id="69f54-138">[Mac용 Visual Studio에서 개인 정보 설정을 관리하는 방법입니다](https://docs.microsoft.com/visualstudio/mac/visual-studio-experience-improvement-program).</span><span class="sxs-lookup"><span data-stu-id="69f54-138">[How to manage privacy settings in Visual Studio for Mac](https://docs.microsoft.com/visualstudio/mac/visual-studio-experience-improvement-program).</span></span>
- <span data-ttu-id="69f54-139">[Visual Studio Code에서 원격 분석 보고를 비활성화하는 방법입니다](https://code.visualstudio.com/docs/supporting/faq#_how-to-disable-telemetry-reporting).</span><span class="sxs-lookup"><span data-stu-id="69f54-139">[How to disable telemetry reporting in Visual Studio Code](https://code.visualstudio.com/docs/supporting/faq#_how-to-disable-telemetry-reporting).</span></span>

#### <a name="exporting-or-deleting-data"></a><span data-ttu-id="69f54-140">데이터 내보내기 또는 삭제</span><span class="sxs-lookup"><span data-stu-id="69f54-140">Exporting or deleting data</span></span>

<span data-ttu-id="69f54-p106">컨트롤러는 Visual Studio 제품군 또는 Microsoft 확장이 등록되는 방법에 따라 데이터 주체에서 수집한 사용자 지정 데이터 및 시스템 생성 로그를 두 가지 방법 중 하나로 관리할 수 있습니다. 경우에 따라 두 가지 방법을 모두 사용해야 합니다. 두 가지 방법 모두 컨트롤러가 해당 방법으로 관리되는 활동 기록의 복사본을 다운로드할 수 있습니다. AAD 또는 MSA 계정의 폐쇄는 관련 Visual Studio 사용자 지정 데이터를 삭제하고 이러한 제품과 관련된 시스템 생성 로그에서 개인 식별 가능한 데이터를 익명화합니다. 익명화된 시스템 생성 로그는 18개월 동안 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="69f54-p106">Controllers can manage customer data and system-generated logs collected from their data subjects by one of two methods, depending upon how their Visual Studio Family product or Microsoft extensions were registered. In some cases, both methods must be used. Both methods allow Controllers to download a copy of their activity history managed by that method. Closure of an AAD or MSA account deletes associated Visual Studio customer data, and anonymizes personally identifiable data in system-generated logs pertaining to these products. Anonymized system-generated logs are retained for no more than 18 months.</span></span>

- <span data-ttu-id="69f54-146">Azure 테넌트가 지원하는 계정(&mdash;예를 들어, Azure 구독과 관련된 AAD 계정 또는 MSA 계정&mdash;)을 사용하여 Visual Studio 제품군 제품을 등록한 사용자는 [GDPR에 대한 Azure 데이터 주체 요청](gdpr-dsr-azure.md)의 지침을 따를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69f54-146">Users that have registered a Visual Studio Family product by using an account that is backed by an Azure tenant&mdash;for example, AAD account or  MSA account associated with an Azure subscription&mdash;can follow the instructions in [Azure Data Subject Requests for the GDPR](gdpr-dsr-azure.md).</span></span>
- <span data-ttu-id="69f54-p107">Azure 테넌트가 지원하는 계정 없이 Visual Studio 제품군 제품을 등록한 사용자(&mdash;예: Microsoft 계정(MSA)을 사용하는 많은 계정&mdash;)는 자신의 Microsoft 계정을 통해 사용할 수 있는 [웹 기반 Microsoft 개인 정보 보호 센터](https://aka.ms/userprivacysite)를 사용하여 여러 Microsoft 서비스 전반의 Microsoft 계정과 연결된 활동 데이터를 보고, 제어하고 삭제할 수 있습니다. 이 시나리오에서 사용자는 개인 데이터에 대한 컨트롤러입니다.</span><span class="sxs-lookup"><span data-stu-id="69f54-p107">Users that have registered a Visual Studio Family product without an account that is backed by an Azure tenant&mdash;for example many accounts using a Microsoft Account (MSA)&mdash;can use [the web-based Microsoft Privacy Response Center](https://aka.ms/userprivacysite) available through their Microsoft account to view, control, and delete activity data tied to their Microsoft account across multiple Microsoft services. In this scenario, the user is a controller for their own personal data.</span></span>

> [!NOTE]
> <span data-ttu-id="69f54-149">MSA 계정 홀더가 자신의 계정을 삭제하면 Azure 테넌트가 계정을 지원했는지 여부에 상관없이 이들 제품과 관련된 모든 개인 식별 데이터가 삭제되고 시스템 생성 로그는 익명화됩니다.</span><span class="sxs-lookup"><span data-stu-id="69f54-149">When an MSA account holder deletes their account, all their personally identifiable data pertaining to these products is deleted, whether the account is backed by an Azure tenant or not, and system-generated logs are anonymized.</span></span>

<span data-ttu-id="69f54-p108">Visual Studio 2013의 경우, 수집하는 데이터가 익명화됩니다. Visual Studio 2012 이전 릴리스의 경우, 데이터를 확인하는 즉시 삭제합니다. 두 경우 모두 나중에 보고 내보내거나 삭제할 항목이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="69f54-p108">For Visual Studio 2013, the data we collect is anonymized. For Visual Studio 2012 and prior releases, we immediately delete the data upon receipt. In both cases, there is nothing to view, export, or delete at a later time.</span></span>

## <a name="visual-studio-developer-community"></a><span data-ttu-id="69f54-153">Visual Studio 개발자 커뮤니티</span><span class="sxs-lookup"><span data-stu-id="69f54-153">Visual Studio Developer Community</span></span>

<span data-ttu-id="69f54-p109">[개발자 커뮤니티](https://developercommunity.visualstudio.com) 웹사이트를 통한 [일반 데이터 보호 규정(GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) 요청을 지원합니다. 피드백 데이터를 보고 내보내거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69f54-p109">We support [General Data Protection Regulation (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) requests through the [Developer Community](https://developercommunity.visualstudio.com) website. You can View, Export, or Delete your feedback data.</span></span>

### <a name="personal-data-we-collect"></a><span data-ttu-id="69f54-156">수집한 개인 데이터</span><span class="sxs-lookup"><span data-stu-id="69f54-156">Personal data we collect</span></span>

<span data-ttu-id="69f54-p110">Microsoft는 사용자가 Visual Studio 제품군 제품에 대해 보고한 문제를 재현하고 해결하는 데 도움을 주는 데이터를 수집합니다. 개인 데이터에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="69f54-p110">Microsoft collects data to help us reproduce and troubleshoot issues you report with Visual Studio Family products. This data includes personal data and public feedback. Personal data includes:</span></span>

- <span data-ttu-id="69f54-160">[개발자 커뮤니티](https://developercommunity.visualstudio.com) 프로필 정보</span><span class="sxs-lookup"><span data-stu-id="69f54-160">Your [Developer Community](https://developercommunity.visualstudio.com) profile information;</span></span>
- <span data-ttu-id="69f54-161">기본 설정 및 알림</span><span class="sxs-lookup"><span data-stu-id="69f54-161">Preferences and notifications;</span></span>
- <span data-ttu-id="69f54-162">[Visual Studio에 문제를 보고](https://docs.microsoft.com/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017)하거나 [개발자 커뮤니티](https://developercommunity.visualstudio.com)를 통해 제공한 첨부 파일 및 시스템 생성 로그</span><span class="sxs-lookup"><span data-stu-id="69f54-162">Attachments and system-generated logs you provided by [reporting a problem in Visual Studio](https://docs.microsoft.com/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017) or through [Developer Community](https://developercommunity.visualstudio.com);</span></span>
- <span data-ttu-id="69f54-163">투표</span><span class="sxs-lookup"><span data-stu-id="69f54-163">Your votes.</span></span>

<span data-ttu-id="69f54-164">공개 피드백에는 문제, 메모, 솔루션이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="69f54-164">Public feedback includes: reported problems, comments, and solutions.</span></span>

### <a name="how-users-can-control-personal-data"></a><span data-ttu-id="69f54-165">사용자가 개인 데이터를 제어하는 방법</span><span class="sxs-lookup"><span data-stu-id="69f54-165">How users can control personal data</span></span>

#### <a name="view"></a><span data-ttu-id="69f54-166">보기</span><span class="sxs-lookup"><span data-stu-id="69f54-166">View</span></span>

<span data-ttu-id="69f54-167">피드백 관련 데이터를 보려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="69f54-167">To View your feedback-related data, follow these steps:</span></span>

1. <span data-ttu-id="69f54-p111">[개발자 커뮤니티](https://developercommunity.visualstudio.com)에 로그인합니다. 오른쪽 상단에서 프로필을 클릭하고 **프로필 및 기본 설정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="69f54-p111">Sign into [Developer Community](https://developercommunity.visualstudio.com). From the top right corner, click on your profile and select **Profile and Preferences**.</span></span>
2. <span data-ttu-id="69f54-170">**프로필**, **알림**, **활동** 및 **첨부 파일** 탭 중 하나를 클릭하면 피드백 시스템에 제출된 데이터를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69f54-170">Click on any of the **Profile**, **Notifications**, **Activity**, and **Attachments** tabs to view the data submitted to the feedback systems.</span></span>
   1. <span data-ttu-id="69f54-171">**프로필**은 사용자 이름, 전자 메일 주소, 정보 등이 포함된 [개발자 커뮤니티](https://developercommunity.visualstudio.com)를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="69f54-171">**Profile** refers to your [Developer Community](https://developercommunity.visualstudio.com) profile, including user name, email address, about, etc.</span></span>
   2. <span data-ttu-id="69f54-172">**알림**은 받은 전자 메일 알림을 제어하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="69f54-172">**Notifications** is how you control the email notifications you receive.</span></span>
   3. <span data-ttu-id="69f54-173">**활동**은 활동 중인(게시 및 메모 포함 등) 피드백 항목 및 수행한 활동을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="69f54-173">**Activity** will give you the feedback items you have been active on (posted, commented, etc.), and the activities performed.</span></span>
   4. <span data-ttu-id="69f54-174">**첨부 파일**은 `FileName was attached to the problem "ProblemName" Tue, Apr 10, 18 2:27 PM`과 같은 형식의 첨부 파일 기록 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="69f54-174">**Attachments** is a list of your attachment history in a format like `FileName was attached to the problem "ProblemName" Tue, Apr 10, 18 2:27 PM`.</span></span>

#### <a name="export"></a><span data-ttu-id="69f54-175">내보내기</span><span class="sxs-lookup"><span data-stu-id="69f54-175">Export</span></span>

<span data-ttu-id="69f54-p112">피드백 데이터를 DSR의 일부로 내보낼 수 있습니다. 다음을 포함하는 하나 이상의 .zip 보관함을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="69f54-p112">You can export your feedback data as part of DSR. We will create one or more .zip archives that will include:</span></span>

- <span data-ttu-id="69f54-178">[개발자 커뮤니티](https://developercommunity.visualstudio.com) 프로필 정보</span><span class="sxs-lookup"><span data-stu-id="69f54-178">Your [Developer Community](https://developercommunity.visualstudio.com) profile information;</span></span>
- <span data-ttu-id="69f54-179">기본 설정 및 알림 설정</span><span class="sxs-lookup"><span data-stu-id="69f54-179">Preferences and notification settings;</span></span>
- <span data-ttu-id="69f54-180">[Visual Studio에 문제를 보고](https://docs.microsoft.com/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017)하거나 [개발자 커뮤니티](https://developercommunity.visualstudio.com)를 통해 제공한 첨부 파일</span><span class="sxs-lookup"><span data-stu-id="69f54-180">Attachments you provided by [reporting a problem in Visual Studio](https://docs.microsoft.com/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017) or through [Developer Community](https://developercommunity.visualstudio.com).</span></span>

> [!NOTE]
> <span data-ttu-id="69f54-181">보관함에서 제공한 설명, 솔루션, 보고된 문제 등 공개 피드백은 제외됩니다.</span><span class="sxs-lookup"><span data-stu-id="69f54-181">We will exclude the following public feedback you have provided from your archive: comments, solutions, reported problems.</span></span>

<span data-ttu-id="69f54-182">내보내기를 시작하려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="69f54-182">To start an Export, follow these steps:</span></span>

1. <span data-ttu-id="69f54-p113">[개발자 커뮤니티](https://developercommunity.visualstudio.com)에 로그인합니다. 오른쪽 상단에서 프로필을 클릭하고 **프로필 및 기본 설정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="69f54-p113">Sign into [Developer Community](https://developercommunity.visualstudio.com). From the top right corner, click on your profile and select **Profile and Preferences**.</span></span>
2. <span data-ttu-id="69f54-185">**개인 정보 보호** 탭을 클릭하고\*\* 보관함 만들기\*\*를 클릭하여 데이터 내보내기를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="69f54-185">Click the **Privacy** tab, and then click **Create an archive** to request exporting your data.</span></span>
3. <span data-ttu-id="69f54-p114">**보관함 상태**가 업데이트되어 데이터 준비 중임을 나타냅니다. 데이터를 사용할 수 있게 되기까지 시간은 내보내려는 데이터 양에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="69f54-p114">The **Archive Status** will update to show that we are preparing the data. The length of time before the data is available depends on the amount of data we need to export.</span></span>
4. <span data-ttu-id="69f54-188">데이터가 준비되면 전자 메일이 수신됩니다.</span><span class="sxs-lookup"><span data-stu-id="69f54-188">Once the data is ready, we will send you an email.</span></span>
5. <span data-ttu-id="69f54-189">전자 메일에서 **다운로드 보관함**을 클릭하거나 개인 정보 보호 탭으로 돌아가서 데이터를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="69f54-189">Click **Download Archive** in the email, or go back to the Privacy tab to download your data.</span></span>

> [!NOTE]
> - <span data-ttu-id="69f54-190">알림 탭에서 알림을 받지 않기로 선택한 경우 전자 메일을 보내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="69f54-190">We will not send email if you chose not to receive notifications in the Notifications tab.</span></span>
> - <span data-ttu-id="69f54-191">다시 내보내기를 요청하면 기존 보관함을 제거하고 새로운 보관함을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="69f54-191">If you request Export again, we will remove your old archive and create a new one.</span></span>

#### <a name="delete"></a><span data-ttu-id="69f54-192">삭제</span><span class="sxs-lookup"><span data-stu-id="69f54-192">Delete</span></span>

<span data-ttu-id="69f54-193">삭제하면 [개발자 커뮤니티](https://developercommunity.visualstudio.com)에서 다음 사용자 정보가 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="69f54-193">Deleting will remove the following information about you from [Developer Community](https://developercommunity.visualstudio.com):</span></span>

- <span data-ttu-id="69f54-194">프로필 정보</span><span class="sxs-lookup"><span data-stu-id="69f54-194">Profile information;</span></span>
- <span data-ttu-id="69f54-195">기본 설정 및 알림 설정</span><span class="sxs-lookup"><span data-stu-id="69f54-195">Preferences and notification settings;</span></span>
- <span data-ttu-id="69f54-196">[Visual Studio에 문제를 보고](https://docs.microsoft.com/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017)하거나 [개발자 커뮤니티](https://developercommunity.visualstudio.com)를 통해 제공한 첨부 파일</span><span class="sxs-lookup"><span data-stu-id="69f54-196">Attachments you provided by [reporting a problem in Visual Studio](https://docs.microsoft.com/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017) or through [Developer Community](https://developercommunity.visualstudio.com).</span></span>
- <span data-ttu-id="69f54-197">투표</span><span class="sxs-lookup"><span data-stu-id="69f54-197">Your votes</span></span>

> [!NOTE]
> <span data-ttu-id="69f54-198">귀하는 설명, 솔루션, 보고한 문제 등의 공개 정보는 삭제되지 않지만 익명화됩니다.</span><span class="sxs-lookup"><span data-stu-id="69f54-198">We will not delete, but will anonymize, the following public information: your comments, your solutions, problems that you reported.</span></span>
>
> [!IMPORTANT]
> <span data-ttu-id="69f54-199">AAD 또는 MSA 계정을 삭제하면 [개발자 커뮤니티](https://developercommunity.visualstudio.com)의 삭제 프로세스가 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="69f54-199">Delete of an AAD or MSA account triggers the Delete process for [Developer Community](https://developercommunity.visualstudio.com).</span></span>

<span data-ttu-id="69f54-200">삭제를 시작하려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="69f54-200">To initiate a Delete, follow these steps:</span></span>

1. <span data-ttu-id="69f54-p115">[개발자 커뮤니티](https://developercommunity.visualstudio.com)에 로그인합니다. 오른쪽 상단에서 프로필을 클릭하고 **프로필 및 기본 설정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="69f54-p115">Sign into [Developer Community](https://developercommunity.visualstudio.com). From the top right corner, click on your profile and select **Profile and Preferences**.</span></span>
2. <span data-ttu-id="69f54-203">**개인 정보 보호** 탭을 클릭한 다음 **데이터 및 계정 삭제**를 클릭하여 데이터 삭제를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="69f54-203">Click the **Privacy** tab, and then click **Delete your data and account** to start deleting your data.</span></span>
3. <span data-ttu-id="69f54-204">확인 화면이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="69f54-204">A confirmation screen will appear.</span></span>
4. <span data-ttu-id="69f54-205">상자에 “삭제”를 입력하고 **내 계정 삭제**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="69f54-205">Type "delete" in the box, and then click **Delete my account**.</span></span>

<span data-ttu-id="69f54-206">**내 계정 삭제:** 를 클릭하면</span><span class="sxs-lookup"><span data-stu-id="69f54-206">Once you click **Delete my account:**</span></span>

- <span data-ttu-id="69f54-207">사용자가 로그아웃됩니다.</span><span class="sxs-lookup"><span data-stu-id="69f54-207">We will sign you out.</span></span>
- <span data-ttu-id="69f54-208">[개발자 커뮤니티](https://developercommunity.visualstudio.com) 계정, 개인 데이터, 첨부 파일을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="69f54-208">We will delete your [Developer Community](https://developercommunity.visualstudio.com) account, your personal data, and attachments.</span></span>
- <span data-ttu-id="69f54-p116">사용자의 공개 피드백을 익명화합니다. 공개 피드백은 개발자 커뮤니티에서 사용할 수 있으며 익명 사용자가 신고한 것으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="69f54-p116">We will anonymize your public feedback. Your public feedback will remain available on Developer Community, and will be indicated as reported by an Anonymous user.</span></span>
- <span data-ttu-id="69f54-211">계정이 삭제되면 더 이상 시스템에 존재하지 않으므로 전자 메일이 전송되지 않습니다. </span><span class="sxs-lookup"><span data-stu-id="69f54-211">We won't email you after we delete your account, because you will no longer be present in the system.</span></span>
- <span data-ttu-id="69f54-212">새 문제를 보고하거나 [개발자 커뮤니티](https://developercommunity.visualstudio.com)에 로그인하면 새 사용자로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="69f54-212">If you report a new problem or log into [Developer Community](https://developercommunity.visualstudio.com), you will be identified as a new user.</span></span>
- <span data-ttu-id="69f54-213">[개발자 커뮤니티](https://developercommunity.visualstudio.com)에서 계정을 삭제하면 다른 Microsoft 서비스에서 계정을 삭제하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="69f54-213">If you delete your account from [Developer Community](https://developercommunity.visualstudio.com), we will not delete it from other Microsoft services.</span></span>

## <a name="xamarin-forums-and-bugzilla"></a><span data-ttu-id="69f54-214">Xamarin 포럼 및 Bugzilla</span><span class="sxs-lookup"><span data-stu-id="69f54-214">Xamarin Forums and Bugzilla</span></span>

### <a name="personal-data-we-collect"></a><span data-ttu-id="69f54-215">수집한 개인 데이터</span><span class="sxs-lookup"><span data-stu-id="69f54-215">Personal Data We Collect</span></span>

<span data-ttu-id="69f54-p117">[Xamarin 포럼](https://forums.xamarin.com) 사용자 커뮤니티 및 [Xamarin Bugzilla](https://bugzilla.xamarin.com/) 버그 보고 웹사이트를 통해 Microsoft는 Microsoft 제품 및 서비스 관련 문제를 재현하고 해결하는 데 도움이 되도록 제공한 데이터를 수집합니다. 이 데이터에는 개인 데이터 및 공개 피드백이 있습니다. 수집한 개인 데이터는 사용자 계정 데이터(예: Xamarin 포럼 또는 Bugzilla 계정 관련 사용자 이름 및 전자 메일 주소)이며 수집한 공개 피드백에는 Xamarin 포럼 또는 Xamarin Bugzilla 버그 보고 웹사이트를 통해 제공한 버그, 문제, 메모, 솔루션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69f54-p117">Through the [Xamarin Forums](https://forums.xamarin.com) user community and [Xamarin Bugzilla](https://bugzilla.xamarin.com/) bug reporting websites, Microsoft collects data you provide to help us reproduce and troubleshoot issues you may have with Microsoft products and services. This data includes personal data and public feedback. The personal data we collect is user account data (for example, user names and email addresses associated with your Xamarin Forums or Bugzilla accounts), and the public feedback we collect includes bugs, problems, comments, and solutions you provide via the Xamarin Forums or Xamarin Bugzilla bug reporting website.</span></span>

### <a name="how-you-can-control-your-data"></a><span data-ttu-id="69f54-219">데이터를 제어하는 방법</span><span class="sxs-lookup"><span data-stu-id="69f54-219">How You Can Control Your Data</span></span>

#### <a name="xamarin-forums"></a><span data-ttu-id="69f54-220">Xamarin 포럼</span><span class="sxs-lookup"><span data-stu-id="69f54-220">Xamarin Forums</span></span>

##### <a name="view"></a><span data-ttu-id="69f54-221">보기</span><span class="sxs-lookup"><span data-stu-id="69f54-221">View</span></span>

<span data-ttu-id="69f54-p118">활성 Xamarin 포럼 계정이 있는 사용자는 Xamarin 포럼 계정 페이지에서 개인 데이터와 공개 피드백(예: 게시한 스레드 및 포스트 전부)을 볼 수 있습니다. 사용자는 계정 페이지를 통해 개인 데이터를 편집할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69f54-p118">Users with active Xamarin Forums accounts may view their personal data and public feedback (for example, all of their posted threads and posts) from their Xamarin Forums account page. Users may also edit their personal data through their account page.</span></span>

##### <a name="export"></a><span data-ttu-id="69f54-224">내보내기</span><span class="sxs-lookup"><span data-stu-id="69f54-224">Export</span></span>

<span data-ttu-id="69f54-p119">Xamarin 포럼은 타사, Vanilla 포럼에 의해 호스트됩니다. 공개 데이터 내보내기를 요청하려면 사용자는 forums@xamarin.com(Xamarin 팀에서 모니터링함)에 문의해야 합니다. 그러면 Vanilla 포럼과 직접 작업하여 이 요청을 처리하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="69f54-p119">Xamarin Forums are hosted by a third party, Vanilla Forums. To request export of your public data, users should contact forums@xamarin.com (monitored by the Xamarin team). We will then work directly with Vanilla Forums to process this request.</span></span>

##### <a name="delete"></a><span data-ttu-id="69f54-228">삭제</span><span class="sxs-lookup"><span data-stu-id="69f54-228">Delete</span></span>

<span data-ttu-id="69f54-p120">Xamarin 포럼은 타사, Vanilla 포럼에 의해 호스트됩니다. 개인 및 공개 데이터의 삭제를 요청하려면 사용자는 forums@xamarin.com(Xamarin 팀에서 모니터링함)에 문의해야 합니다. 그러면 사용자의 개인 데이터 삭제 요청을 직접 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="69f54-p120">Xamarin Forums are hosted by a third party, Vanilla Forums. To request deletion of your personal and public data, users should contact forums@xamarin.com (monitored by the Xamarin team). We will then manually service the user's personal data deletion request.</span></span>

#### <a name="bugzilla-for-xamarin"></a><span data-ttu-id="69f54-232">Xamarin용 Bugzilla</span><span class="sxs-lookup"><span data-stu-id="69f54-232">Bugzilla for Xamarin</span></span>

##### <a name="view"></a><span data-ttu-id="69f54-233">보기</span><span class="sxs-lookup"><span data-stu-id="69f54-233">View</span></span>

<span data-ttu-id="69f54-234">활성 Xamarin Bugzilla 계정이 있는 사용자는 Xamarin Bugzilla 홈 페이지에서 적절한 링크를 클릭하여 보고한 모든 버그와 버그에 추가한 모든 메모를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69f54-234">Users with active Xamarin Bugzilla accounts can view all bugs they've reported and all comments they've added to bugs by clicking the appropriate links on the Xamarin Bugzilla home page.</span></span>

##### <a name="export"></a><span data-ttu-id="69f54-235">내보내기</span><span class="sxs-lookup"><span data-stu-id="69f54-235">Export</span></span>

<span data-ttu-id="69f54-236">개인 데이터 내보내기가 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="69f54-236">Exporting of personal data is not supported.</span></span>

##### <a name="delete"></a><span data-ttu-id="69f54-237">삭제</span><span class="sxs-lookup"><span data-stu-id="69f54-237">Delete</span></span>

<span data-ttu-id="69f54-p121">Xamarin의 Bugzilla 버그 보고 웹사이트를 통해 연결에 사용된 개인 데이터의 삭제를 요청하려면, 사용자는 [사용자 기본 설정 페이지](https://bugzilla.xamarin.com/userprefs.cgi)로 이동하고 **계정 탭 닫기**를 선택하여 Xamarin Bugzilla 계정을 닫을 수 있습니다. Bugzilla 암호를 입력하고 계정이 영구 삭제된다는 사실을 확인하는 상자를 선택합니다. 사용자가 Xamarin Bugzilla에 게시한 공개 피드백(예: 버그, 문제, 메모, 솔루션)이 삭제 요청을 수신한 후 삭제되지 않습니다. 공개 피드백은 대신 사용자가 삭제 요청을 제출하여 만들어진 모든 공개 피드백과 연관된 이름 및 전자 메일 주소를 제거하여 익명화됩니다.</span><span class="sxs-lookup"><span data-stu-id="69f54-p121">To request deletion of personal data used in connection with Xamarin's Bugzilla bug reporting website, users can close their Xamarin Bugzilla account by going to the [user preferences page](https://bugzilla.xamarin.com/userprefs.cgi) and choosing the **Close Account tab**. Enter your Bugzilla password and check the box confirming that you understand that this will permanently delete your account. Public feedback (for example, bugs, problems, comments, and solutions) that users have posted to the Xamarin Bugzilla will not be deleted after receipt of a delete request. Public feedback will instead be anonymized by removing the name and email address associated with any public feedback created by the user submitting the delete request.</span></span>

## <a name="nuget"></a><span data-ttu-id="69f54-241">NuGet</span><span class="sxs-lookup"><span data-stu-id="69f54-241">NuGet</span></span>

<span data-ttu-id="69f54-242">NuGet에 대한 DSR의 자세한 내용은 [NuGet 사용자 데이터 요청](https://docs.microsoft.com/nuget/policies/data-requests)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="69f54-242">For more information on DSR for NuGet.org, see [NuGet User Data Requests](https://docs.microsoft.com/nuget/policies/data-requests).</span></span>

## <a name="aspnet"></a><span data-ttu-id="69f54-243">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="69f54-243">ASP.NET</span></span>

<span data-ttu-id="69f54-244">ASP.NET 웹사이트에 대한 DSR의 자세한 내용은 [ASP.NET 웹사이트 및 GDPR 데이터 주체 요청 처리](https://www.asp.net/gdpr)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="69f54-244">For information on DSR for the ASP.NET website, see [The ASP.NET Website and GDPR Data Subject Request processing](https://www.asp.net/gdpr).</span></span>

## <a name="iisnet"></a><span data-ttu-id="69f54-245">IIS.NET</span><span class="sxs-lookup"><span data-stu-id="69f54-245">IIS.NET</span></span>

<span data-ttu-id="69f54-246">IIS.NET 웹사이트에 대한 DSR의 자세한 내용은 [IIS.NET 웹사이트 및 GDPR 데이터 주체 요청 처리](https://www.iis.net/gdpr)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="69f54-246">For information on DSR for the IIS.NET website, see [The IIS.NET Website and GDPR Data Subject Request processing](https://www.iis.net/gdpr).</span></span>

## <a name="other-visual-studio-family-services"></a><span data-ttu-id="69f54-247">기타 Visual Studio 제품군 서비스</span><span class="sxs-lookup"><span data-stu-id="69f54-247">Other Visual Studio Family Services</span></span>

### <a name="surveymonkey"></a><span data-ttu-id="69f54-248">SurveyMonkey</span><span class="sxs-lookup"><span data-stu-id="69f54-248">SurveyMonkey</span></span>

<span data-ttu-id="69f54-p122">때때로 고객들을 초대하여 SurverMonkey를 통해 이러한 제품들에 대한 피드백을 제공하도록 합니다. 이 데이터는 28일 이내에 삭제됩니다. 이러한 제품에 대한 데이터 주체 요청을 처리할 때 인증된 설문 조사 응답이 있는 경우 데이터 주체 요청을 내보내고 삭제할 때 이를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="69f54-p122">From time to time, we invite customers to provide feedback on these products via SurveyMonkey. This data is deleted within 28 days. When servicing data subject requests for these products, if we have authenticated survey responses we include them in export and delete data subject requests.</span></span>

### <a name="uservoice"></a><span data-ttu-id="69f54-252">UserVoice</span><span class="sxs-lookup"><span data-stu-id="69f54-252">UserVoice</span></span>

<span data-ttu-id="69f54-p123">고객을 초대하여 UserVoice.com 사이트에서 이러한 제품들에 대한 제품 제안 사항을 제공합니다. 이러한 사이트는 UserVoice에서 독립적으로 작동되며 데이터 주체 요청은 UserVoice에서 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="69f54-p123">We invite customers to provide product suggestions at UserVoice.com sites for these products. These sites are independently operated by UserVoice, and data subject requests are managed by UserVoice.</span></span>

- [https://visualstudio.uservoice.com/](https://visualstudio.uservoice.com/)
- [https://aspnet.uservoice.com/](https://aspnet.uservoice.com/)
- [https://xamarin.uservoice.com/](https://xamarin.uservoice.com/)

<span data-ttu-id="69f54-255">이 데이터에 대한 데이터 주체 요청의 경우, [데이터를 내보내는 방법](https://feedback.uservoice.com/knowledgebase/articles/1850245-export-my-personal-data) 또는 [데이터를 삭제하는 방법](https://feedback.uservoice.com/knowledgebase/articles/1848856-delete-my-profile-information)에 대한 UserVoice 참고 자료를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="69f54-255">For data subject requests on this data, see the UserVoice guidance on [how to export your data](https://feedback.uservoice.com/knowledgebase/articles/1850245-export-my-personal-data) or on [how to delete your data](https://feedback.uservoice.com/knowledgebase/articles/1848856-delete-my-profile-information).</span></span>

## <a name="learn-more"></a><span data-ttu-id="69f54-256">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="69f54-256">Learn more</span></span>

- [<span data-ttu-id="69f54-257">일반적으로 사용할 수 있는 엔터프라이즈 소프트웨어 제품의 고객에 대한 Microsoft의 GDPR 약속</span><span class="sxs-lookup"><span data-stu-id="69f54-257">Microsoft's GDPR Commitments to Customers of our Generally Available Enterprise Software Products</span></span>](https://docs.microsoft.com/legal/gdpr)
- [<span data-ttu-id="69f54-258">Microsoft 보안 센터</span><span class="sxs-lookup"><span data-stu-id="69f54-258">Microsoft Trust Center</span></span>](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
- [<span data-ttu-id="69f54-259">서비스 보안 포털</span><span class="sxs-lookup"><span data-stu-id="69f54-259">Service Trust portal</span></span>](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted)
- [<span data-ttu-id="69f54-260">Microsoft 개인 정보 대시보드</span><span class="sxs-lookup"><span data-stu-id="69f54-260">Microsoft Privacy Dashboard</span></span>](https://account.microsoft.com/privacy)
- [<span data-ttu-id="69f54-261">Microsoft 개인 정보 응답 센터</span><span class="sxs-lookup"><span data-stu-id="69f54-261">Microsoft Privacy Response Center</span></span>](https://aka.ms/userprivacysite)
- [<span data-ttu-id="69f54-262">GDPR에 대한 Azure 데이터 주체 요청</span><span class="sxs-lookup"><span data-stu-id="69f54-262">Azure Data Subject Requests for the GDPR</span></span>](gdpr-dsr-azure.md)
