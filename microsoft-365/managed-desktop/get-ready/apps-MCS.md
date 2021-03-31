---
title: Microsoft 컨설팅 서비스 활용
description: MCS와 함께 앱을 패키지로 구성하기 위한 준비 및 단계
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 1441ca3305a5f3e5a83ddd5e1547812f08d7d96b
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445699"
---
# <a name="working-with-microsoft-consulting-services"></a><span data-ttu-id="4a065-104">Microsoft 컨설팅 서비스 활용</span><span class="sxs-lookup"><span data-stu-id="4a065-104">Working with Microsoft Consulting Services</span></span>

<span data-ttu-id="4a065-105">MCS(Microsoft Consulting Services)에 참여하여 Microsoft Managed Desktop에서 사용하기 위해 패키지된 앱을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a065-105">You can engage with Microsoft Consulting Services (MCS) to get your apps packaged for use with Microsoft Managed Desktop.</span></span> <span data-ttu-id="4a065-106">정확한 정보를 확인하려면 계정 담당자와 함께 MCS에 문의하고 특정 앱 패키징 프로젝트의 범위를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4a065-106">For exact details, work with your account representative to contact MCS and scope your specific app packaging project.</span></span>

## <a name="roles-and-responsibilities"></a><span data-ttu-id="4a065-107">역할 및 책임</span><span class="sxs-lookup"><span data-stu-id="4a065-107">Roles and responsibilities</span></span>

<span data-ttu-id="4a065-108">MCS 앱 패키징을 사용하려면 **다음 요소를 제공해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="4a065-108">To work with MCS app packaging, **you must provide these elements**:</span></span>

- <span data-ttu-id="4a065-109">원본 설치 관리자 파일(예: setup.exe 또는 .msi)입니다.</span><span class="sxs-lookup"><span data-stu-id="4a065-109">The source installer files (for example, setup.exe or .msi).</span></span>
- <span data-ttu-id="4a065-110">최종 설치의 모양에 대한 세부 정보를 지정하는 설치 지침입니다.</span><span class="sxs-lookup"><span data-stu-id="4a065-110">The installation instructions, specifying details about how the final installation should look.</span></span> <span data-ttu-id="4a065-111">예를 들어 앱에 대한 데스크톱 바로 가기가 있나요?</span><span class="sxs-lookup"><span data-stu-id="4a065-111">For example, should there be a desktop shortcut to the app?</span></span> <span data-ttu-id="4a065-112">앱의 표시 여부는 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="4a065-112">What should the app's visibility be?</span></span> <span data-ttu-id="4a065-113">앱이 서버에 연결해야 하는 경우 어떤 서버가 연결하나요?</span><span class="sxs-lookup"><span data-stu-id="4a065-113">Should the app connect to a server and if so, which one?</span></span> <span data-ttu-id="4a065-114">자세한 내용은 응용 프로그램 패키징 요청 [템플릿 을 참조합니다.](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx)</span><span class="sxs-lookup"><span data-stu-id="4a065-114">For details, see the [application packaging request template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx).</span></span>
- <span data-ttu-id="4a065-115">사용자 환경에서 앱이 필요한 경우 작동하는지 확인하기 위해 자체 승인 테스트를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a065-115">You must perform your own acceptance testing to verify that the app works as you need it to in your environment.</span></span>

<span data-ttu-id="4a065-116">**MCS는 다음 작업을 관리합니다.**</span><span class="sxs-lookup"><span data-stu-id="4a065-116">**MCS will take care of these actions:**</span></span>

- <span data-ttu-id="4a065-117">Microsoft Managed Desktop 환경에서 앱이 금지되거나 제한되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="4a065-117">Checking whether the app is prohibited or restricted in the Microsoft Managed Desktop environment.</span></span>
- <span data-ttu-id="4a065-118">Windows 10과의 호환성을 보장하기 위해 앱의 설치, 시작 및 제거 테스트</span><span class="sxs-lookup"><span data-stu-id="4a065-118">Testing of installation, starting, and uninstallation of the app to ensure compatibility with Windows 10.</span></span> <span data-ttu-id="4a065-119">MCS가 호환성 문제를 발견하면 수정을 위해 [앱을 App Assure](https://docs.microsoft.com/fasttrack/products-and-capabilities#app-assure) 프로그램으로 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4a065-119">If MCS discovers a compatibility issue, they will hand off the app to the [App Assure](https://docs.microsoft.com/fasttrack/products-and-capabilities#app-assure) program for remediation.</span></span>
- <span data-ttu-id="4a065-120">앱을 사양에 패키징한 다음 Microsoft Intune을 사용하여 앱 배포를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="4a065-120">Packaging the app to your specification and then testing app deployment by using Microsoft Intune.</span></span>

## <a name="app-delivery-schedule"></a><span data-ttu-id="4a065-121">앱 배달 일정</span><span class="sxs-lookup"><span data-stu-id="4a065-121">App delivery schedule</span></span>

<span data-ttu-id="4a065-122">Microsoft Managed Desktop 포털에 앱 정보를 업로드하여 패키징 프로세스를 시작하세요.</span><span class="sxs-lookup"><span data-stu-id="4a065-122">Start the packaging process by uploading the app information to the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="4a065-123">패키징 팀은 매주 목요일에 새 제출을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="4a065-123">The packaging team reviews new submissions every Thursday.</span></span> <span data-ttu-id="4a065-124">검토 및 패키징 후 패키지된 앱은 다음 금요일에 배달됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a065-124">After review and packaging, the packaged apps are delivered the following Friday.</span></span> <span data-ttu-id="4a065-125">시작을 위해 일주일에 최대 5개의 앱을 패키지로 구성할 수 있지만, 서비스는 요구에 따라 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a065-125">Up to five apps per week can be packaged to start but the service can scale to meet your needs.</span></span>

![목요일(이 예제의 21일), 미디어 유효성 검사, 다음 주 월요일(25일)에 패키징, 다음 금요일(29일)에 앱 배달을 표시하는 일정](../../media/MCS-cal.png)

<span data-ttu-id="4a065-127">앱이 제공된 후 알림을 하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a065-127">You'll be notified once the app has been delivered.</span></span> <span data-ttu-id="4a065-128">이때 Microsoft Managed Desktop 포털에서 승인 테스트를 수행하고 작업을 승인하는 데 21일이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a065-128">At that point, you have 21 days to perform acceptance testing and approve the work in the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="4a065-129">수용 테스트 중에 앱에 문제가 발견되면 Microsoft Managed Desktop 포털에서 앱을 거부하고 MCS 패키지러와 전자 메일을 통해 연결하여 문제를 이해하고 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="4a065-129">If discover some problem with the app during your acceptance testing, reject the app in the Microsoft Managed Desktop portal and you will be connected via email with an MCS packager to understand and resolve the issue.</span></span>

## <a name="testing-accounts-and-environment"></a><span data-ttu-id="4a065-130">계정 및 환경 테스트</span><span class="sxs-lookup"><span data-stu-id="4a065-130">Testing accounts and environment</span></span>

<span data-ttu-id="4a065-131">패키징 팀에서 Microsoft Intune으로의 마이그레이션을 완료하려면 다음의 특정 권한을 제공하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4a065-131">For the packaging team to complete the migration to Microsoft Intune, we recommend that you provide certain permissions:</span></span>
 
-   <span data-ttu-id="4a065-132">패키지를 통해 앱을 추가하고 할당할 수 있는 Microsoft Intune의 앱 배포 기능에 대한 액세스</span><span class="sxs-lookup"><span data-stu-id="4a065-132">Access to Microsoft Intune’s App Deployment capabilities for the packager to add and assign the app</span></span> 
-   <span data-ttu-id="4a065-133">패키지러가 앱을 테스트할 수 있도록 테스트 그룹, 사용자 계정 및 라이선스</span><span class="sxs-lookup"><span data-stu-id="4a065-133">Test groups, user accounts, and licenses for the packagers to be able to test the apps</span></span>

<span data-ttu-id="4a065-134">MCS는 해당 사용 권한을 사용하여 다음 작업을 수행하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a065-134">MCS will use those permissions to perform the following actions:</span></span>
 
-   <span data-ttu-id="4a065-135">Microsoft Managed Desktop에 대해 구성된 가상 머신에서 앱이 작동하는지 보장</span><span class="sxs-lookup"><span data-stu-id="4a065-135">Ensuring that the app works on virtual machine configured for Microsoft Managed Desktop</span></span>
-   <span data-ttu-id="4a065-136">사용자에게 배포하기 위해 Microsoft Intune에 앱 업로드</span><span class="sxs-lookup"><span data-stu-id="4a065-136">Uploading the app to Microsoft Intune for deployment to your users</span></span>

<span data-ttu-id="4a065-137">이러한 권한이 없는 경우 MCS가 앞으로 이동할 수 있지만 응용 프로그램을 사용자 환경에 업로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4a065-137">Without these permissions, it is possible for MCS to move forward, but they will not be able to upload the applications to your environment.</span></span>
