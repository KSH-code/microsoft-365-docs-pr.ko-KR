---
title: 앱 컨트롤
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: e9d33df0ae11d01c8c214fbe0f001a16e8f4908d
ms.sourcegitcommit: 63887d742c59cc660fc85537b335e98a9dc66fbe
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/18/2020
ms.locfileid: "45170724"
---
# <a name="app-control"></a><span data-ttu-id="f90d3-103">앱 컨트롤</span><span class="sxs-lookup"><span data-stu-id="f90d3-103">App control</span></span>

<span data-ttu-id="f90d3-104">앱 컨트롤은 클라이언트 장치에서 코드를 실행 하는 것을 제한 하는 Microsoft Managed Desktop의 선택적 보안 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="f90d3-104">App control is an optional security practice in Microsoft Managed Desktop that restricts the execution of code on client devices.</span></span> <span data-ttu-id="f90d3-105">이 컨트롤은 고객이 승인한 게시자 목록에 의해 서명 된 코드만 실행할 수 있도록 요구 하 여 맬웨어 또는 악성 스크립트의 위험을 완화 합니다.</span><span class="sxs-lookup"><span data-stu-id="f90d3-105">This control mitigates the risk of malware or malicious scripts by requiring that only code signed by a customer-approved list of publishers can run.</span></span> <span data-ttu-id="f90d3-106">이 컨트롤은 다양 한 보안 이점을 제공 하지만, 주로 클라이언트 기반 익스플로잇 으로부터 데이터 및 id를 보호 하는 데 목적이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f90d3-106">There are many security benefits from this control, but it primarily aims to protect data and identity from client-based exploits.</span></span>

<span data-ttu-id="f90d3-107">Microsoft Managed Desktop은 핵심 생산성 시나리오를 가능 하 게 하는 기본 정책을 만들어 앱 제어 정책 관리를 간소화 합니다.</span><span class="sxs-lookup"><span data-stu-id="f90d3-107">Microsoft Managed Desktop simplifies the management of app control policies by creating a base policy that enables core productivity scenarios.</span></span> <span data-ttu-id="f90d3-108">해당 환경의 앱 및 스크립트와 관련 된 추가 서명자에 대 한 신뢰를 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f90d3-108">You can extend trust to additional signers that are specific to the apps and scripts in your environment.</span></span> 


<span data-ttu-id="f90d3-109">모든 보안 기술에는 사용자 환경, 보안 및 비용 간의 균형이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f90d3-109">Any security technology requires a balance among user experience, security, and cost.</span></span> <span data-ttu-id="f90d3-110">앱 컨트롤을 사용 하면 사용자 환경에서 악성 소프트웨어의 위협을 줄일 수 있지만 최종 사용자와 IT 관리자를 위한 추가 작업에는 결과가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f90d3-110">App control reduces the threat of malicious software in your environment, but there are consequences to the end user and additional actions for your IT administrator.</span></span>

<span data-ttu-id="f90d3-111">**추가 보안:**</span><span class="sxs-lookup"><span data-stu-id="f90d3-111">**Additional security:**</span></span>

<span data-ttu-id="f90d3-112">앱 제어 정책에서 신뢰 하지 않는 앱 또는 스크립트가 장치에서 실행 되지 않도록 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f90d3-112">Apps or scripts that are not trusted by the app control policy are blocked from running on devices.</span></span>

<span data-ttu-id="f90d3-113">**추가 책임:**</span><span class="sxs-lookup"><span data-stu-id="f90d3-113">**Your additional responsibilities:**</span></span>

- <span data-ttu-id="f90d3-114">응용 프로그램 제어 정책에 의해 차단 되는지 여부를 확인 하기 위해 앱을 테스트할 책임이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f90d3-114">You are responsible for testing your apps to identify whether they would be blocked by the application control policy.</span></span>
- <span data-ttu-id="f90d3-115">앱이 차단 되는 경우에는 필요한 서명자 정보를 식별 하 고 관리 포털을 통해 변경을 요청 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f90d3-115">If an app is (or would be) blocked, you are responsible for identifying the needed signer details and requesting a change through the Admin portal.</span></span>

<span data-ttu-id="f90d3-116">**Microsoft Managed Desktop 역할:**</span><span class="sxs-lookup"><span data-stu-id="f90d3-116">**Microsoft Managed Desktop responsibilities:**</span></span>

- <span data-ttu-id="f90d3-117">Microsoft Managed Desktop은 M365 앱, Windows, 팀, OneDrive 등의 핵심 Microsoft 제품을 사용할 수 있도록 하는 기본 정책을 유지 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="f90d3-117">Microsoft Managed Desktop maintains the base policy that enables core Microsoft products like M365 Apps, Windows, Teams, OneDrive, and so on.</span></span>
- <span data-ttu-id="f90d3-118">Microsoft Managed Desktop 신뢰할 수 있는 서명자를 삽입 하 고 업데이트 된 정책을 장치에 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="f90d3-118">Microsoft Managed Desktop inserts your trusted signers and deploys the updated policy to your devices.</span></span>


## <a name="managing-trust-in-applications"></a><span data-ttu-id="f90d3-119">응용 프로그램의 신뢰 관리</span><span class="sxs-lookup"><span data-stu-id="f90d3-119">Managing trust in applications</span></span>

<span data-ttu-id="f90d3-120">Microsoft Managed Desktop은 Microsoft 기술의 핵심 구성 요소를 신뢰 하는 기본 정책을 curates 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f90d3-120">Microsoft Managed Desktop curates a base policy that trusts the core components of Microsoft technologies.</span></span> <span data-ttu-id="f90d3-121">그런 다음 Microsoft Managed Desktop에 이미 믿을 수 있는 사용자를 알려 서 자신의 응용 프로그램 및 스크립트에 대 한 트러스트를 *추가* 합니다.</span><span class="sxs-lookup"><span data-stu-id="f90d3-121">You then *add* trust for your own applications and scripts by informing Microsoft Managed Desktop which of them you already trust.</span></span>

### <a name="base-policy"></a><span data-ttu-id="f90d3-122">기본 정책</span><span class="sxs-lookup"><span data-stu-id="f90d3-122">Base policy</span></span>

<span data-ttu-id="f90d3-123">Microsoft Managed Desktop, Microsoft cybersecurity 전문가와 공동 작업을 수행 하면 코드 컴파일 또는 신뢰할 수 없는 파일 실행과 같은 위험한 활동을 차단 하면서 Microsoft Intune을 통해 배포 되는 대부분의 앱을 사용할 수 있도록 하는 표준 정책을 만들고 유지 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="f90d3-123">Microsoft Managed Desktop, in collaboration with Microsoft cybersecurity experts, creates and maintains a standard policy that enables most apps deployed through Microsoft Intune while blocking dangerous activities like code compilation or execution of untrusted files.</span></span>

<span data-ttu-id="f90d3-124">기본 정책은 소프트웨어 실행을 제한 하는 다음과 같은 접근 방식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f90d3-124">The base policy takes the following approach to restricting software execution:</span></span>

- <span data-ttu-id="f90d3-125">관리자가 실행 한 파일을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f90d3-125">Files run by administrators will be allowed to run.</span></span>
- <span data-ttu-id="f90d3-126">사용자가 쓸 수 없는 디렉터리에 *없는* 위치에 있는 파일은 실행이 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f90d3-126">Files in locations that are *not* in user-writable directories will be allowed to run.</span></span>
- <span data-ttu-id="f90d3-127">[신뢰할 수 있는 서명자](#signer-requests)가 파일에 서명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f90d3-127">Files are signed by a [trusted signer](#signer-requests).</span></span>
- <span data-ttu-id="f90d3-128">Microsoft에서 서명한 대부분의 파일은 실행 되지만, 코드 컴파일과 같은 높은 위험 작업을 방지 하기 위해 일부는 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f90d3-128">Most files signed by Microsoft will run, however some are blocked to prevent high-risk actions like code compilation.</span></span>


<span data-ttu-id="f90d3-129">관리자가 아닌 사용자가 앱 또는 스크립트를 장치에 추가 했을 수 있습니다 (즉, 사용자가 쓰기 가능한 디렉터리에 있는 경우). 관리자가 이미 특별히 허용한 경우가 아니면 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f90d3-129">If a user other than an administrator could have added an app or script to a device (that is, it's in a user-writable directory), we won't allow it to execute unless it has already been specifically allowed by an administrator.</span></span> <span data-ttu-id="f90d3-130">사용자가 맬웨어 설치를 tricked 하는 경우, 사용자가 실행 하는 앱의 취약성으로 인해 맬웨어가 설치 하려고 하거나, 사용자가 고의로 허용 되지 않은 앱 이나 스크립트를 실행 하려고 하면 정책 실행이 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f90d3-130">If a user is tricked into trying to install malware, if a vulnerability in an app the user runs attempts to install malware, or if a user intentionally tries to run an unauthorized app or script, our policy will stop execution.</span></span>

### <a name="signer-requests"></a><span data-ttu-id="f90d3-131">서명자 요청</span><span class="sxs-lookup"><span data-stu-id="f90d3-131">Signer requests</span></span>

<span data-ttu-id="f90d3-132">*서명자 요청*을 관리 하 여 신뢰할 수 있는 소프트웨어 공급 업체에서 제공 하는 앱을 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f90d3-132">You inform us of which apps are provided by software vendors you trust by filing a *signer request*.</span></span> <span data-ttu-id="f90d3-133">이렇게 하면 해당 신뢰 정보가 기본 응용 프로그램 제어 정책에 추가 되 고 해당 게시자의 인증서로 서명 된 모든 소프트웨어가 장치에서 실행 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f90d3-133">By doing so, we add that trust information into the baseline application control policy and allow any software signed with that publisher's certificate to run on your devices.</span></span>

## <a name="audit-and-enforced-policies"></a><span data-ttu-id="f90d3-134">감사 및 적용 정책</span><span class="sxs-lookup"><span data-stu-id="f90d3-134">Audit and Enforced policies</span></span>

<span data-ttu-id="f90d3-135">Microsoft Managed Desktop은 두 가지 Microsoft Intune 정책을 사용 하 여 앱 제어권을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f90d3-135">Microsoft Managed Desktop uses two Microsoft Intune policies to provide app control:</span></span>

### <a name="audit-policy"></a><span data-ttu-id="f90d3-136">감사 정책</span><span class="sxs-lookup"><span data-stu-id="f90d3-136">Audit policy</span></span>
<span data-ttu-id="f90d3-137">이 정책은 앱 또는 스크립트가 적용 된 정책에 의해 차단 되는지 여부를 기록 하는 로그를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f90d3-137">This policy creates logs to record whether an app or script would be blocked by the Enforced policy.</span></span> <span data-ttu-id="f90d3-138">감사 정책은 앱 제어 규칙을 적용 하지 않으며 응용 프로그램에 게시자 예외가 필요한 지 여부를 확인 하기 위한 테스트 목적으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f90d3-138">Audit policies don't enforce app control rules and are meant for testing purposes to identify whether an application will require a publisher exemption.</span></span> <span data-ttu-id="f90d3-139">지정 된 앱 또는 스크립트의 실행 또는 설치를 차단 하는 대신 이벤트 뷰어에 경고 (8003 또는 8006 이벤트)를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f90d3-139">It logs warnings (8003 or 8006 events) in Event Viewer instead of blocking the execution or installation of specified apps or script.</span></span>

### <a name="enforced-policy"></a><span data-ttu-id="f90d3-140">적용 정책</span><span class="sxs-lookup"><span data-stu-id="f90d3-140">Enforced policy</span></span>
<span data-ttu-id="f90d3-141">이 정책은 앱 또는 스크립트가 차단 될 때마다 트러스트 되지 않은 앱 및 스크립트를 실행 하 고 로그를 만들 수 없도록 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="f90d3-141">This policy blocks untrusted apps and scripts from running and creates logs whenever an app or script is blocked.</span></span> <span data-ttu-id="f90d3-142">적용 된 정책에 의해 표준 사용자는 사용자가 쓰기 가능한 디렉터리에 저장 되어 있는 앱 이나 스크립트를 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f90d3-142">Enforced policies prevent standard users from executing apps or scripts stored in user-writable directories.</span></span>

<span data-ttu-id="f90d3-143">테스트 그룹의 장치에는 감사 정책이 적용 되므로 응용 프로그램에서 문제를 발생 시킬 것인지 여부를 확인 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f90d3-143">Devices in the Test group have an Audit policy applied so that you can use them to validate whether any applications will cause issues.</span></span> <span data-ttu-id="f90d3-144">다른 모든 그룹 (첫째, 빠르게, 광범위 함)은 적용 되는 정책을 사용 하므로 해당 그룹의 최종 사용자는 신뢰할 수 없는 앱 이나 스크립트를 실행 하지 못하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f90d3-144">All other groups (First, Fast, and Broad) use an Enforced policy, so end users in those groups won't be able to run untrusted apps or scripts.</span></span>







