---
title: Microsoft Managed Desktop의 인쇄 리소스 준비
description: 인쇄 작업을 원활 하 게 하기 위한 중요 한 단계
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: 1588a2c91bcbe0bd381acb6be4f9bd5562810860
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2020
ms.locfileid: "46530250"
---
# <a name="prepare-printing-resources-for-microsoft-managed-desktop"></a><span data-ttu-id="64f79-104">Microsoft Managed Desktop의 인쇄 리소스 준비</span><span class="sxs-lookup"><span data-stu-id="64f79-104">Prepare printing resources for Microsoft Managed Desktop</span></span>

<span data-ttu-id="64f79-105">Microsoft Managed Desktop에서 등록할 준비가 되 면 인쇄 요구 사항을 평가 하 고 사용자 환경에 적합 한 접근 방식을 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64f79-105">As you get ready to enroll in Microsoft Managed Desktop, you should evaluate your printing requirements and determine the right approach for your environment.</span></span> <span data-ttu-id="64f79-106">다음 세 가지 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64f79-106">You have three options:</span></span>
 
- <span data-ttu-id="64f79-107">Microsoft 하이브리드 클라우드 인쇄 솔루션을 배포 하 여 마이크로소프트의 관리 되는 데스크톱 장치가 프린터를 쉽게 검색할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="64f79-107">Deploy the Microsoft hybrid cloud print solution to make it easy for Microsoft Managed Desktop devices to discover printers.</span></span> <span data-ttu-id="64f79-108">자세한 내용은 [Windows Server 하이브리드 클라우드 인쇄 배포](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="64f79-108">For more information, see [Deploy Windows Server Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span></span>
- <span data-ttu-id="64f79-109">사용자 지정 PowerShell 스크립트를 사용 하 여 프린터를 직접 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="64f79-109">Deploy printers directly by using a custom PowerShell script.</span></span> <span data-ttu-id="64f79-110">이 작업을 수행 하려면 [로컬 프린터 설정](#set-up-local-printers) 섹션에 나와 있는 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="64f79-110">Follow the steps in the [Set up local printers](#set-up-local-printers) section to do this.</span></span>
- <span data-ttu-id="64f79-111">Azure Active Directory 도메인에 가입 된 Windows 10 장치와 호환 되는 타사 클라우드 인쇄 솔루션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="64f79-111">Use a non-Microsoft cloud printing solution that is compatible with Windows 10 devices that are joined to an Azure Active Directory domain.</span></span> <span data-ttu-id="64f79-112">이 솔루션은 Microsoft Managed Desktop의 소프트웨어 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64f79-112">The solution must meet the software requirements for Microsoft Managed Desktop.</span></span> <span data-ttu-id="64f79-113">자세한 내용은 [Microsoft Managed Desktop app 요구 사항을](../service-description/mmd-app-requirements.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="64f79-113">For more information, see [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md).</span></span>
 
<span data-ttu-id="64f79-114">Microsoft 업데이트나 Microsoft Store에서 사용할 수 없는 프린터 드라이버를 사용 하는 경우에는 사용자를 직접 구입 하 여 microsoft Intune을 사용 하 여 Microsoft Managed Desktop devices 배포를 위해 패키지화 되도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64f79-114">In all cases, if the printer drivers are not available from Microsoft Update or the Microsoft Store, you'll have to obtain them yourself and have them packaged for deployment to your Microsoft Managed Desktop devices with Microsoft Intune.</span></span> <span data-ttu-id="64f79-115">자세한 내용은 [Intune 독립 실행형-Win32 앱 관리](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="64f79-115">For more, see [Intune Standalone - Win32 app management](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management)</span></span>

## <a name="set-up-local-printers"></a><span data-ttu-id="64f79-116">로컬 프린터 설정</span><span class="sxs-lookup"><span data-stu-id="64f79-116">Set up local printers</span></span>

<span data-ttu-id="64f79-117">사용자 지정 PowerShell 스크립트를 사용 하 여 프린터를 배포 하기로 결정 하 고 인쇄 리소스를 준비한 후에는 다음 단계를 수행 하 여 공유 프린터를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64f79-117">If you've decided to deploy printers by using a custom PowerShell script and have prepared the printing resources, follow these steps to have shared printers deployed:</span></span>

1.  <span data-ttu-id="64f79-118">Microsoft Managed Desktop 포털로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="64f79-118">Navigate to the Microsoft Managed Desktop portal.</span></span>
2.  <span data-ttu-id="64f79-119">다음 세부 정보를 제공 하 여 관리 포털의 **지원 > 지원 요청** 섹션에서 *프린터 배포* 라는 요청을 제출 합니다.</span><span class="sxs-lookup"><span data-stu-id="64f79-119">Submit a request labeled *Printer deployment* in the **Support > Support requests** section of the Admin Portal, providing these details:</span></span>
    - <span data-ttu-id="64f79-120">Microsoft Managed Desktop 장치용으로 배포 해야 하는 공유 프린터 위치의 모든 UNC 경로</span><span class="sxs-lookup"><span data-stu-id="64f79-120">All UNC paths to shared printer locations that will need to be deployed for Microsoft Managed Desktop devices</span></span>
    - <span data-ttu-id="64f79-121">이러한 공유 프린터에 액세스 해야 하는 사용자 그룹</span><span class="sxs-lookup"><span data-stu-id="64f79-121">User groups that require access to these shared printers</span></span>
3.  <span data-ttu-id="64f79-122">관리자 포털을 사용 하면 요청이 완료 된 시기를 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64f79-122">Using the Admin Portal, we'll let you know when the request has been completed.</span></span> <span data-ttu-id="64f79-123">처음에는 테스트 배포 그룹의 장치에만 구성을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="64f79-123">Initially we'll only deploy the configuration to devices in the Test deployment group.</span></span>
4.  <span data-ttu-id="64f79-124">구성이 예상 대로 작동 하는지 여부를 테스트 하 고 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64f79-124">You must test and confirm whether the configuration works as you expect.</span></span> <span data-ttu-id="64f79-125">지원 요청의 **토론** 탭을 사용 하 여 회신 하 여 테스트를 완료 한 시기를 알려주세요.</span><span class="sxs-lookup"><span data-stu-id="64f79-125">Reply by using the **Discussion** tab in the Support request to let us know when you've completed your testing.</span></span>
5.  <span data-ttu-id="64f79-126">그런 다음 구성을 다른 배포 그룹에 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="64f79-126">We'll then deploy the configuration to the other deployment groups.</span></span>
