---
title: 앱 제어
description: 응용 프로그램 제어 및 신뢰를 사용하는 방법
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 6f5cc923b5a18b1f45dd186e88228db8c3a891cc
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841306"
---
# <a name="app-control"></a><span data-ttu-id="90e73-104">앱 제어</span><span class="sxs-lookup"><span data-stu-id="90e73-104">App control</span></span>

<span data-ttu-id="90e73-105">앱 컨트롤은 클라이언트 장치에서 코드 실행을 제한하는 Microsoft Managed Desktop의 선택적 보안 사례입니다.</span><span class="sxs-lookup"><span data-stu-id="90e73-105">App control is an optional security practice in Microsoft Managed Desktop that restricts the execution of code on client devices.</span></span> <span data-ttu-id="90e73-106">이 컨트롤은 고객이 승인한 게시자 목록에서 서명한 코드만 실행할 수 있도록 하여 맬웨어 또는 악성 스크립트의 위험을 완화합니다.</span><span class="sxs-lookup"><span data-stu-id="90e73-106">This control mitigates the risk of malware or malicious scripts by requiring that only code signed by a customer-approved list of publishers can run.</span></span> <span data-ttu-id="90e73-107">이 컨트롤에는 많은 보안 이점이 있지만 주로 클라이언트 기반 악용으로부터 데이터 및 ID를 보호하는 것을 목표로 합니다.</span><span class="sxs-lookup"><span data-stu-id="90e73-107">There are many security benefits from this control, but it primarily aims to protect data and identity from client-based exploits.</span></span>

<span data-ttu-id="90e73-108">Microsoft Managed Desktop은 핵심 생산성 시나리오를 가능하게 하는 기본 정책을 만들어 앱 제어 정책 관리를 간소화합니다.</span><span class="sxs-lookup"><span data-stu-id="90e73-108">Microsoft Managed Desktop simplifies the management of app control policies by creating a base policy that enables core productivity scenarios.</span></span> <span data-ttu-id="90e73-109">환경의 앱 및 스크립트와 관련이 있는 다른 서명자에 대한 신뢰를 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90e73-109">You can extend trust to other signers that are specific to the apps and scripts in your environment.</span></span> 


<span data-ttu-id="90e73-110">모든 보안 기술을 사용하려면 사용자 환경, 보안 및 비용의 균형을 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="90e73-110">Any security technology requires a balance among user experience, security, and cost.</span></span> <span data-ttu-id="90e73-111">앱 컨트롤을 사용하면 환경에서 악성 소프트웨어의 위협을 줄일 수 있지만, 사용자에 대한 결과 및 IT 관리자를 위한 추가 작업이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90e73-111">App control reduces the threat of malicious software in your environment, but there are consequences to the user and further actions for your IT administrator.</span></span>

<span data-ttu-id="90e73-112">**추가 보안:**</span><span class="sxs-lookup"><span data-stu-id="90e73-112">**Additional security:**</span></span>

<span data-ttu-id="90e73-113">앱 제어 정책에서 신뢰하지 않는 앱 또는 스크립트는 장치에서 실행되지 못하게 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="90e73-113">Apps or scripts that are not trusted by the app control policy are blocked from running on devices.</span></span>

<span data-ttu-id="90e73-114">**추가 책임:**</span><span class="sxs-lookup"><span data-stu-id="90e73-114">**Your additional responsibilities:**</span></span>

- <span data-ttu-id="90e73-115">응용 프로그램 제어 정책에 의해 차단될지 여부를 식별하기 위해 앱을 테스트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="90e73-115">You are responsible for testing your apps to identify whether they would be blocked by the application control policy.</span></span>
- <span data-ttu-id="90e73-116">앱이 차단된 경우 필요한 서명자 세부 정보를 식별하고 관리 포털을 통해 변경을 요청해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="90e73-116">If an app is (or would be) blocked, you are responsible for identifying the needed signer details and requesting a change through the Admin portal.</span></span>

<span data-ttu-id="90e73-117">**Microsoft Managed Desktop 책임:**</span><span class="sxs-lookup"><span data-stu-id="90e73-117">**Microsoft Managed Desktop responsibilities:**</span></span>

- <span data-ttu-id="90e73-118">Microsoft Managed Desktop은 M365 앱, Windows, Teams, OneDrive와 같은 핵심 Microsoft 제품을 사용할 수 있도록 하는 기본 정책을 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="90e73-118">Microsoft Managed Desktop maintains the base policy that enables core Microsoft products like M365 Apps, Windows, Teams, OneDrive, and so on.</span></span>
- <span data-ttu-id="90e73-119">Microsoft Managed Desktop은 신뢰할 수 있는 서명자 및 업데이트된 정책을 장치에 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="90e73-119">Microsoft Managed Desktop inserts your trusted signers and deploys the updated policy to your devices.</span></span>


## <a name="managing-trust-in-applications"></a><span data-ttu-id="90e73-120">응용 프로그램의 트러스트 관리</span><span class="sxs-lookup"><span data-stu-id="90e73-120">Managing trust in applications</span></span>

<span data-ttu-id="90e73-121">Microsoft Managed Desktop은 Microsoft 기술의 핵심 구성 요소를 신뢰하는 기본 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="90e73-121">Microsoft Managed Desktop curates a base policy that trusts the core components of Microsoft technologies.</span></span> <span data-ttu-id="90e73-122">그런 *다음* Microsoft Managed Desktop에 이미 신뢰하는 응용 프로그램 및 스크립트에 대한 신뢰를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="90e73-122">You then *add* trust for your own applications and scripts by informing Microsoft Managed Desktop which of them you already trust.</span></span>

### <a name="base-policy"></a><span data-ttu-id="90e73-123">기본 정책</span><span class="sxs-lookup"><span data-stu-id="90e73-123">Base policy</span></span>

<span data-ttu-id="90e73-124">Microsoft 사이버 보안 전문가와 협력하여 Microsoft Managed Desktop은 코드 컴파일 또는 보안되지 않은 파일의 실행과 같은 위험한 활동을 차단하면서 Microsoft Intune을 통해 배포되는 대부분의 앱을 사용할 수 있는 표준 정책을 만들고 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="90e73-124">Microsoft Managed Desktop, in collaboration with Microsoft cybersecurity experts, creates, and maintains a standard policy that enables most apps deployed through Microsoft Intune while blocking dangerous activities like code compilation or execution of untrusted files.</span></span>

<span data-ttu-id="90e73-125">기본 정책은 다음과 같은 방식으로 소프트웨어 실행을 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="90e73-125">The base policy takes the following approach to restricting software execution:</span></span>

- <span data-ttu-id="90e73-126">관리자가 실행한 파일은 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90e73-126">Files run by administrators will be allowed to run.</span></span>
- <span data-ttu-id="90e73-127">사용자가 덮어  사용할 수 있는 폴더에 없는 위치의 파일은 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90e73-127">Files in locations that are *not* in user-writable directories will be allowed to run.</span></span>
- <span data-ttu-id="90e73-128">파일은 신뢰할 수 있는 [서명자에 의해 서명됩니다.](#signer-requests)</span><span class="sxs-lookup"><span data-stu-id="90e73-128">Files are signed by a [trusted signer](#signer-requests).</span></span>
- <span data-ttu-id="90e73-129">Microsoft에서 서명한 대부분의 파일은 실행될 것이지만 일부는 코드 컴파일과 같은 높은 위험 작업을 방지하기 위해 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="90e73-129">Most files signed by Microsoft will run, however some are blocked to prevent high-risk actions like code compilation.</span></span>


<span data-ttu-id="90e73-130">관리자 외의 사용자가 장치에 앱 또는 스크립트를 추가할 수 있는 경우(즉, 사용자가 써서 사용할 수 있는 디렉터리에 있는 경우) 관리자가 특별히 허용하지 않은 경우 실행을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="90e73-130">If a user other than an administrator could have added an app or script to a device (that is, it's in a user-writable directory), we won't allow it to execute unless it has already been specifically allowed by an administrator.</span></span> <span data-ttu-id="90e73-131">사용자가 맬웨어를 설치하도록 속이거나, 사용자가 실행되는 앱의 취약점이 맬웨어를 설치하려고 시도하거나, 사용자가 의도적으로 권한이 없는 앱 또는 스크립트를 실행하려고 하면 정책 실행이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="90e73-131">If a user is tricked into trying to install malware, if a vulnerability in an app the user runs attempts to install malware, or if a user intentionally tries to run an unauthorized app or script, our policy will stop execution.</span></span>

### <a name="signer-requests"></a><span data-ttu-id="90e73-132">서명자 요청</span><span class="sxs-lookup"><span data-stu-id="90e73-132">Signer requests</span></span>

<span data-ttu-id="90e73-133">서명자 요청을 제출하여 신뢰하는 소프트웨어 게시자가 제공하는 앱을 *알려 드립니다.*</span><span class="sxs-lookup"><span data-stu-id="90e73-133">You inform us of which apps are provided by software publishers you trust by filing a *signer request*.</span></span> <span data-ttu-id="90e73-134">이렇게 하면 해당 신뢰 정보를 기준 응용 프로그램 제어 정책에 추가하고 해당 게시자의 인증서로 서명된 소프트웨어가 장치에서 실행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90e73-134">By doing so, we add that trust information into the baseline application control policy and allow any software signed with that publisher's certificate to run on your devices.</span></span>

## <a name="audit-and-enforced-policies"></a><span data-ttu-id="90e73-135">감사 및 적용 정책</span><span class="sxs-lookup"><span data-stu-id="90e73-135">Audit and Enforced policies</span></span>

<span data-ttu-id="90e73-136">Microsoft Managed Desktop은 두 가지 Microsoft Intune 정책을 사용하여 앱 제어를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="90e73-136">Microsoft Managed Desktop uses two Microsoft Intune policies to provide app control:</span></span>

### <a name="audit-policy"></a><span data-ttu-id="90e73-137">감사 정책</span><span class="sxs-lookup"><span data-stu-id="90e73-137">Audit policy</span></span>
<span data-ttu-id="90e73-138">이 정책은 적용 정책에 의해 앱 또는 스크립트가 차단될지 여부를 기록하는 로그를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="90e73-138">This policy creates logs to record whether an app or script would be blocked by the Enforced policy.</span></span> <span data-ttu-id="90e73-139">감사 정책은 앱 제어 규칙을 적용하지 않습니다. 응용 프로그램에 게시자 면제가 필요한지 여부를 식별하기 위한 테스트 목적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="90e73-139">Audit policies don't enforce app control rules and are meant for testing purposes to identify whether an application will require a publisher exemption.</span></span> <span data-ttu-id="90e73-140">지정된 앱 또는 스크립트의 실행 또는 설치를 차단하는 대신 이벤트 뷰어에 경고(8003 또는 8006 이벤트)를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="90e73-140">It logs warnings (8003 or 8006 events) in Event Viewer instead of blocking the execution or installation of specified apps or script.</span></span>

### <a name="enforced-policy"></a><span data-ttu-id="90e73-141">적용된 정책</span><span class="sxs-lookup"><span data-stu-id="90e73-141">Enforced policy</span></span>
<span data-ttu-id="90e73-142">이 정책은 앱 또는 스크립트가 차단될 때마다 트러스터가 실행되지 않는 앱과 스크립트를 차단하고 로그를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="90e73-142">This policy blocks untrusted apps and scripts from running and creates logs whenever an app or script is blocked.</span></span> <span data-ttu-id="90e73-143">적용된 정책은 표준 사용자가 사용자가 작성 가능한 Director에 저장된 앱 또는 스크립트를 실행하지 못하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="90e73-143">Enforced policies prevent standard users from executing apps or scripts stored in user-writable directories.</span></span>

<span data-ttu-id="90e73-144">테스트 그룹의 장치에는 응용 프로그램이 문제를 일으킬 수 있는지 여부를 검사하는 데 사용할 수 있도록 감사 정책이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="90e73-144">Devices in the Test group have an Audit policy applied so that you can use them to validate whether any applications will cause issues.</span></span> <span data-ttu-id="90e73-145">다른 모든 그룹(첫 번째, 빠르기 및 광범위)은 강제 적용 정책을 사용하며, 따라서 해당 그룹의 사용자는 불안정한 앱 또는 스크립트를 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="90e73-145">All other groups (First, Fast, and Broad) use an Enforced policy, so users in those groups won't be able to run untrusted apps or scripts.</span></span>







