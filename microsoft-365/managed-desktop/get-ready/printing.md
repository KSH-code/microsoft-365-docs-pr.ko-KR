---
title: Microsoft Managed Desktop의 인쇄 리소스 준비
description: 인쇄가 원활하게 작동하기 위한 중요 단계
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 971644aafabda733bf745fae278bdfeeed3282e3
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574550"
---
# <a name="prepare-printing-resources-for-microsoft-managed-desktop"></a><span data-ttu-id="e3886-104">Microsoft Managed Desktop의 인쇄 리소스 준비</span><span class="sxs-lookup"><span data-stu-id="e3886-104">Prepare printing resources for Microsoft Managed Desktop</span></span>

<span data-ttu-id="e3886-105">Microsoft Managed Desktop에 등록할 준비가 되면 인쇄 요구 사항을 평가하고 환경에 적합한 방법을 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3886-105">As you get ready to enroll in Microsoft Managed Desktop, you should evaluate your printing requirements and determine the right approach for your environment.</span></span> <span data-ttu-id="e3886-106">다음과 같은 세 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3886-106">You have three options:</span></span>
 
- <span data-ttu-id="e3886-107">Microsoft Managed Desktop 장치가 프린터를 쉽게 검색할 수 있도록 Microsoft 유니버설 인쇄 솔루션을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="e3886-107">Deploy the Microsoft Universal Print solution to make it easy for Microsoft Managed Desktop devices to discover printers.</span></span> <span data-ttu-id="e3886-108">자세한 내용은 유니버설 인쇄 [를 참조하세요.](/universal-print/fundamentals/universal-print-whatis)</span><span class="sxs-lookup"><span data-stu-id="e3886-108">For more information, see [What is Universal Print](/universal-print/fundamentals/universal-print-whatis).</span></span>
- <span data-ttu-id="e3886-109">사용자 지정 PowerShell 스크립트를 사용하여 프린터를 직접 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="e3886-109">Deploy printers directly by using a custom PowerShell script.</span></span> <span data-ttu-id="e3886-110">로컬 프린터 설정 [섹션의 단계를](#set-up-local-printers) 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="e3886-110">Follow the steps in the [Set up local printers](#set-up-local-printers) section.</span></span>
- <span data-ttu-id="e3886-111">Azure Active Directory 도메인에 가입된 Windows 10 장치와 호환되는 Microsoft가 아닌 클라우드 인쇄 솔루션을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="e3886-111">Use a non-Microsoft cloud printing solution that is compatible with Windows 10 devices that are joined to an Azure Active Directory domain.</span></span> <span data-ttu-id="e3886-112">솔루션은 Microsoft Managed Desktop의 소프트웨어 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3886-112">The solution must meet the software requirements for Microsoft Managed Desktop.</span></span> <span data-ttu-id="e3886-113">자세한 내용은 Microsoft Managed Desktop 앱 [요구 사항을 참조하세요.](../service-description/mmd-app-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="e3886-113">For more information, see [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md).</span></span>
 
<span data-ttu-id="e3886-114">모든 경우에 프린터 드라이버를 Microsoft Update 또는 Microsoft Store에서 사용할 수 없는 경우 프린터 드라이버를 직접 얻어 Microsoft Intune을 사용하여 Microsoft Managed Desktop 디바이스에 배포할 수 있도록 패키지로 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3886-114">In all cases, if the printer drivers are not available from Microsoft Update or the Microsoft Store, you'll have to obtain them yourself and have them packaged for deployment to your Microsoft Managed Desktop devices with Microsoft Intune.</span></span> <span data-ttu-id="e3886-115">자세한 내용은 [Intune 독립 실행형 - Win32 앱 관리를 참조하세요.](/mem/intune/apps/apps-win32-app-management)</span><span class="sxs-lookup"><span data-stu-id="e3886-115">For more, see [Intune Standalone - Win32 app management](/mem/intune/apps/apps-win32-app-management)</span></span>

## <a name="set-up-local-printers"></a><span data-ttu-id="e3886-116">로컬 프린터 설정</span><span class="sxs-lookup"><span data-stu-id="e3886-116">Set up local printers</span></span>

<span data-ttu-id="e3886-117">사용자 지정 PowerShell 스크립트를 사용하여 프린터를 배포하기로 결정하고 인쇄 리소스를 준비한 경우 다음 단계에 따라 공유 프린터를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="e3886-117">If you've decided to deploy printers by using a custom PowerShell script and have prepared the printing resources, follow these steps to have shared printers deployed:</span></span>

1.  <span data-ttu-id="e3886-118">Microsoft Managed Desktop 포털로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="e3886-118">Navigate to the Microsoft Managed Desktop portal.</span></span>
2.  <span data-ttu-id="e3886-119">관리 포털의  지원 >  지원 요청 섹션에서 레이블이 붙은 프린터 배포 요청을 제출하여 다음 세부 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e3886-119">Submit a request labeled *Printer deployment* in the **Support > Support requests** section of the Admin Portal, providing these details:</span></span>
    - <span data-ttu-id="e3886-120">Microsoft Managed Desktop 장치에 배포해야 하는 공유 프린터 위치에 대한 모든 UNC 경로</span><span class="sxs-lookup"><span data-stu-id="e3886-120">All UNC paths to shared printer locations that will need to be deployed for Microsoft Managed Desktop devices</span></span>
    - <span data-ttu-id="e3886-121">이러한 공유 프린터에 액세스해야 하는 사용자 그룹</span><span class="sxs-lookup"><span data-stu-id="e3886-121">User groups that require access to these shared printers</span></span>
3.  <span data-ttu-id="e3886-122">관리 포털을 사용하여 요청이 완료된 경우 이를 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3886-122">Using the Admin Portal, we'll let you know when the request has been completed.</span></span> <span data-ttu-id="e3886-123">처음에는 테스트 배포 그룹의 장치에만 구성을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="e3886-123">Initially we'll only deploy the configuration to devices in the Test deployment group.</span></span>
4.  <span data-ttu-id="e3886-124">구성이 예상한 결과로 작동하는지 테스트하고 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3886-124">You must test and confirm whether the configuration works as you expect.</span></span> <span data-ttu-id="e3886-125">테스트 완료  시 알려주기 위해 지원 요청의 토론 탭을 사용하여 회신합니다.</span><span class="sxs-lookup"><span data-stu-id="e3886-125">Reply by using the **Discussion** tab in the Support request to let us know when you've completed your testing.</span></span>
5.  <span data-ttu-id="e3886-126">그런 다음 구성을 다른 배포 그룹에 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="e3886-126">We'll then deploy the configuration to the other deployment groups.</span></span>

## <a name="steps-to-get-ready"></a><span data-ttu-id="e3886-127">준비 단계</span><span class="sxs-lookup"><span data-stu-id="e3886-127">Steps to get ready</span></span>

1. <span data-ttu-id="e3886-128">Microsoft Managed Desktop의 선행 [준비를 검토합니다.](prerequisites.md)</span><span class="sxs-lookup"><span data-stu-id="e3886-128">Review [Prerequisites for Microsoft Managed Desktop](prerequisites.md).</span></span>
2. <span data-ttu-id="e3886-129">준비 [평가 도구를 사용합니다.](readiness-assessment-tool.md)</span><span class="sxs-lookup"><span data-stu-id="e3886-129">Use [Readiness assessment tools](readiness-assessment-tool.md).</span></span>
3. [<span data-ttu-id="e3886-130">게스트 계정에 대한 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="e3886-130">Prerequisites for guest accounts</span></span>](guest-accounts.md)
4. [<span data-ttu-id="e3886-131">Microsoft Managed Desktop의 네트워크 구성</span><span class="sxs-lookup"><span data-stu-id="e3886-131">Network configuration for Microsoft Managed Desktop</span></span>](network.md)
5. [<span data-ttu-id="e3886-132">Microsoft Managed Desktop 인증서 및 네트워크 프로필 준비</span><span class="sxs-lookup"><span data-stu-id="e3886-132">Prepare certificates and network profiles for Microsoft Managed Desktop</span></span>](certs-wifi-lan.md)
6. [<span data-ttu-id="e3886-133">Microsoft Managed Desktop의 온-프레미스 리소스 액세스 준비</span><span class="sxs-lookup"><span data-stu-id="e3886-133">Prepare on-premises resources access for Microsoft Managed Desktop</span></span>](authentication.md)
7. [<span data-ttu-id="e3886-134">Microsoft Managed Desktop의 앱</span><span class="sxs-lookup"><span data-stu-id="e3886-134">Apps in Microsoft Managed Desktop</span></span>](apps.md)
8. [<span data-ttu-id="e3886-135">Microsoft Managed Desktop의 매핑된 드라이브 준비</span><span class="sxs-lookup"><span data-stu-id="e3886-135">Prepare mapped drives for Microsoft Managed Desktop</span></span>](mapped-drives.md)
9. <span data-ttu-id="e3886-136">[Microsoft Managed Desktop용](printing.md) 인쇄 리소스 준비(이 문서)</span><span class="sxs-lookup"><span data-stu-id="e3886-136">[Prepare printing resources for Microsoft Managed Desktop](printing.md) (This article)</span></span>
