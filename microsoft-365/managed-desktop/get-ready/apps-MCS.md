---
title: Microsoft 컨설팅 서비스 활용
description: 앱을 패키지로 하기 위해 MCS에서 수행 해야 하는 준비 및 단계
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 설명서, 앱, MCS, 패키징
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 0cb4da85b5548ced757197a3af818e212b065b47
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42085945"
---
# <a name="working-with-microsoft-consulting-services"></a><span data-ttu-id="e8fd7-104">Microsoft 컨설팅 서비스 활용</span><span class="sxs-lookup"><span data-stu-id="e8fd7-104">Working with Microsoft Consulting Services</span></span>

<span data-ttu-id="e8fd7-105">MCS (Microsoft 컨설팅 서비스)를 사용 하 여 Microsoft Managed Desktop과 함께 사용할 수 있도록 앱 패키지를 가져올 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8fd7-105">You can engage with Microsoft Consulting Services (MCS) to get your apps packaged for use with Microsoft Managed Desktop.</span></span> <span data-ttu-id="e8fd7-106">자세한 내용은 계정 담당자와 함께 MCS에 문의 하 여 특정 앱 패키징 프로젝트의 범위를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8fd7-106">For exact details, work with your account representative to contact MCS and scope your specific app packaging project.</span></span>

## <a name="roles-and-responsibilities"></a><span data-ttu-id="e8fd7-107">역할 및 책임</span><span class="sxs-lookup"><span data-stu-id="e8fd7-107">Roles and responsibilities</span></span>

<span data-ttu-id="e8fd7-108">MCS 앱 패키지로 작업 하려면 **다음 요소를 제공 해야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="e8fd7-108">To work with MCS app packaging, **you must provide these elements**:</span></span>

- <span data-ttu-id="e8fd7-109">원본 설치 관리자 파일 (예: setup.exe 또는 .msi)</span><span class="sxs-lookup"><span data-stu-id="e8fd7-109">The source installer files (e.g., setup.exe or .msi).</span></span>
- <span data-ttu-id="e8fd7-110">설치 지침에 따라 최종 설치의 모양에 대 한 세부 정보를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8fd7-110">The installation instructions, specifying details about how the final installation should look.</span></span> <span data-ttu-id="e8fd7-111">예를 들어, 앱에 대 한 바탕 화면 바로 가기가 있어야 하나요?</span><span class="sxs-lookup"><span data-stu-id="e8fd7-111">For example, should there be a desktop shortcut to the app?</span></span> <span data-ttu-id="e8fd7-112">앱의 표시 유형</span><span class="sxs-lookup"><span data-stu-id="e8fd7-112">What should the app's visibility be?</span></span> <span data-ttu-id="e8fd7-113">앱이 서버에 연결 되는 경우 (있는 경우)</span><span class="sxs-lookup"><span data-stu-id="e8fd7-113">Should the app connect to a server and if so, which one?</span></span> <span data-ttu-id="e8fd7-114">자세한 내용은 [응용 프로그램 패키징 요청 템플릿을](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e8fd7-114">For details, see the [application packaging request template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx).</span></span>
- <span data-ttu-id="e8fd7-115">자체 승인 테스트를 수행 하 여 사용자 환경에서 앱이 필요한 대로 작동 하는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8fd7-115">You must perform your own acceptance testing to verify that the app works as you need it to in your environment.</span></span>

<span data-ttu-id="e8fd7-116">**MCS에서는 다음 작업을 수행 합니다.**</span><span class="sxs-lookup"><span data-stu-id="e8fd7-116">**MCS will take care of these actions:**</span></span>

- <span data-ttu-id="e8fd7-117">앱이 Microsoft Managed Desktop 환경에서 금지 되거나 제한 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8fd7-117">Checking whether the app is prohibited or restricted in the Microsoft Managed Desktop environment.</span></span>
- <span data-ttu-id="e8fd7-118">앱의 설치, 시작 및 제거를 테스트 하 여 Windows 10과의 호환성을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8fd7-118">Testing of installation, starting, and uninstallation of the app to ensure compatibility with Windows 10.</span></span> <span data-ttu-id="e8fd7-119">MCS에서 호환성 문제가 발견 되 면 앱이 관리 하기 위한 [데스크톱 앱 보증](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) 프로그램에 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8fd7-119">If MCS discovers a compatibility issue, they will hand off the app to the [Desktop App Assure](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) program for remediation.</span></span>
- <span data-ttu-id="e8fd7-120">앱을 사양에 패키징 한 다음 Microsoft Intune을 사용 하 여 앱 배포를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8fd7-120">Packaging the app to your specification and then testing app deployment by using Microsoft Intune.</span></span>

## <a name="app-delivery-schedule"></a><span data-ttu-id="e8fd7-121">앱 배달 일정</span><span class="sxs-lookup"><span data-stu-id="e8fd7-121">App delivery schedule</span></span>

<span data-ttu-id="e8fd7-122">Microsoft Managed Desktop portal에 앱 정보를 업로드 하 여 패키지 프로세스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8fd7-122">Start the packaging process by uploading the app information to the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="e8fd7-123">패키지 팀은 목요일 마다 새 제출을 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8fd7-123">The packaging team reviews new submissions every Thursday.</span></span> <span data-ttu-id="e8fd7-124">검토 및 패키징에 따라 패키징된 앱에는 다음과 같은 금요일이 배달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8fd7-124">After review and packaging, the packaged apps are delivered the following Friday.</span></span> <span data-ttu-id="e8fd7-125">주당 최대 5 개의 앱을 시작 하도록 패키지할 수 있지만 서비스는 사용자의 요구에 맞게 확장 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8fd7-125">Up to five apps per week can be packaged to start but the service can scale to meet your needs.</span></span>

![매월 목요일에 앱 유입량을 표시 하는 달력 (이 예에서는 21), 다음 날에 대 한 패키징 (25) 및 이후 금요일 (29 일)에 대 한 앱 배달](../../media/MCS-cal.png)

<span data-ttu-id="e8fd7-127">앱이 전달 되 면 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8fd7-127">You'll be notified once the app has been delivered.</span></span> <span data-ttu-id="e8fd7-128">이 시점에서 승인 테스트를 수행 하 고 Microsoft Managed Desktop portal에서 작업을 진행 하는 데 21 일이 소요 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8fd7-128">At that point, you have 21 days to perform acceptance testing and sign off on the work in the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="e8fd7-129">승인 테스트 중에 앱에서 문제가 발견 되는 경우 Microsoft Managed Desktop portal에서 앱을 거부 하 고이 문제를 이해 하 고 해결 하기 위해 전자 메일을 통해 MCS 포장기를 통해 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8fd7-129">If discover some problem with the app during your acceptance testing, reject the app in the Microsoft Managed Desktop portal and you will be connected via email with an MCS packager to understand and resolve the issue.</span></span>

## <a name="testing-accounts-and-environment"></a><span data-ttu-id="e8fd7-130">계정 및 환경 테스트</span><span class="sxs-lookup"><span data-stu-id="e8fd7-130">Testing accounts and environment</span></span>

<span data-ttu-id="e8fd7-131">패키징 팀이 Microsoft Intune으로의 마이그레이션을 완료 하려면 특정 사용 권한을 제공 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e8fd7-131">For the packaging team to complete the migration to Microsoft Intune we recommend that you provide certain permissions:</span></span>
 
-   <span data-ttu-id="e8fd7-132">앱 추가 및 할당을 위한 포장기 용 Microsoft Intune 앱 배포 기능에 대 한 액세스 권한</span><span class="sxs-lookup"><span data-stu-id="e8fd7-132">Access to Microsoft Intune’s App Deployment capabilities for the packager to add and assign the app</span></span> 
-   <span data-ttu-id="e8fd7-133">앱을 테스트할 수 있도록 packagers에 대 한 테스트 그룹, 사용자 계정 및 라이선스</span><span class="sxs-lookup"><span data-stu-id="e8fd7-133">Test groups, user accounts, and licenses for the packagers to be able to test the apps</span></span>

<span data-ttu-id="e8fd7-134">MCS는 이러한 권한을 사용 하 여 다음 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8fd7-134">MCS will use those permissions to perform the following actions:</span></span>
 
-   <span data-ttu-id="e8fd7-135">앱이 Microsoft Managed Desktop에 대해 구성 된 가상 컴퓨터에서 작동 하는지 확인</span><span class="sxs-lookup"><span data-stu-id="e8fd7-135">Ensuring that the app works on virtual machine configured for Microsoft Managed Desktop</span></span>
-   <span data-ttu-id="e8fd7-136">사용자에 게 배포 하기 위해 Microsoft Intune에 앱 업로드</span><span class="sxs-lookup"><span data-stu-id="e8fd7-136">Uploading the app to Microsoft Intune for deployment to your users</span></span>

<span data-ttu-id="e8fd7-137">이러한 사용 권한이 없으면 MCS가 앞으로 이동할 수 있지만 사용자 환경에 응용 프로그램을 업로드할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e8fd7-137">Without these permissions, it is possible for MCS to move forward, but they will not be able to upload the applications to your environment.</span></span>


