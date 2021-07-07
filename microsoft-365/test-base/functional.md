---
title: 테스트 기준에 대한 기능 테스트
description: 기존 자동화된 기능 테스트를 통해 응용 프로그램을 테스트하는 방법에 대한 세부 정보
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 7b5cb907756ec0fb746d303b3ab629e912bf9c96
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323226"
---
# <a name="functional-testing"></a><span data-ttu-id="80cb0-103">기능 테스트</span><span class="sxs-lookup"><span data-stu-id="80cb0-103">Functional testing</span></span>

<span data-ttu-id="80cb0-104">소프트웨어 공급업체는 이제 M365용 셀프 서비스 테스트 베이스 포털을 통해 원하는 테스트 프레임워크를 사용하여 사용자 지정 기능 테스트를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80cb0-104">As a software vendor, you can now perform custom functional tests, using the test framework of your choice - via the self-serve Test Base for M365 portal.</span></span> 

<span data-ttu-id="80cb0-105">서비스를 처음 출시할 때 표준화된 스크립팅을 통해 구동되는 미리 정의된 테스트 집합인 기본 제공 테스트를 제공했습니다.</span><span class="sxs-lookup"><span data-stu-id="80cb0-105">When we initially launched the service, we offered the Out-of-box tests, which is a pre-defined set of tests driven through standardized scripting.</span></span> <span data-ttu-id="80cb0-106">그러나 많은 ISV(Independent Software Vendor)에 대해 전체 테스트 범위를 달성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="80cb0-106">This, however, could not achieve full test coverage for many Independent Software Vendors (ISVs).</span></span> 

<span data-ttu-id="80cb0-107">따라서 사용자 의견에 따라 당사는 자동화된 기능 테스트를 업로드하는 기능을 ISV에 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="80cb0-107">Hence, in response to your feedback, we are providing our ISVs with the ability to upload automated functional tests.</span></span>

<span data-ttu-id="80cb0-108">이 기능을 사용 하 고 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="80cb0-108">To use this feature, follow the steps below:</span></span>

1. <span data-ttu-id="80cb0-109">업로드(이진, 종속성 및 스크립트)를 단일 패키지로 .zip 합니다.</span><span class="sxs-lookup"><span data-stu-id="80cb0-109">Upload your files (binaries, dependencies and scripts) as a single .zip package.</span></span>
2. <span data-ttu-id="80cb0-110">다양한 실행 지점에서 테스트 VM(가상 컴퓨터)을 다시부팅할지 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="80cb0-110">Choose if you want to reboot the test Virtual Machines (VMs) at various points of execution.</span></span>
3. <span data-ttu-id="80cb0-111">스크립트에 사용할 수 있는 옵션을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="80cb0-111">Manage available options for your scripts.</span></span>
4. <span data-ttu-id="80cb0-112">실행 중 VM에서 Windows 업데이트를 적용할 시기를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="80cb0-112">Choose when to apply the Windows update on the VM during execution.</span></span>

<span data-ttu-id="80cb0-113">위의 단계에 대한 자세한 설명은 아래에서 강조 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="80cb0-113">Detailed descriptions of the above steps are highlighted below:</span></span>

<span data-ttu-id="80cb0-114">**업로드 테스트 패키지 구성**</span><span class="sxs-lookup"><span data-stu-id="80cb0-114">**Upload a functional test package**</span></span>

<span data-ttu-id="80cb0-115">시작하려면 업로드 페이지로 이동하여 Azure에서 M365 업로드 테스트 기준 포털의 왼쪽 탐색 메뉴에 있는 응용 프로그램 카탈로그 아래에서 새 응용 프로그램을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="80cb0-115">To get started, navigate to the Upload page, select Upload new application under Application catalog on the left-side navigation menu of the Test Base for M365 portal in Azure.</span></span> <span data-ttu-id="80cb0-116">이 경우</span><span class="sxs-lookup"><span data-stu-id="80cb0-116">From there:</span></span>

<span data-ttu-id="80cb0-117">탭 1 - 기본 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="80cb0-117">Tab 1 - Enter basic information.</span></span> <span data-ttu-id="80cb0-118">응용 프로그램의 이름과 버전을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="80cb0-118">Provide the name and version of your application.</span></span> <span data-ttu-id="80cb0-119">테스트 유형 옵션에서 를 ```Functional tests``` 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="80cb0-119">In the Type of test option, select ```Functional tests```.</span></span> 

<span data-ttu-id="80cb0-120">*OOB(Out-of-Box) 옵션은 기본적으로 필요합니다.*</span><span class="sxs-lookup"><span data-stu-id="80cb0-120">*Note that the Out-of-Box (OOB) option is required by default.*</span></span>


![기능 테스트 탭 선택](Media/functional_testing_tab1.png)

<span data-ttu-id="80cb0-122">탭 2 - 업로드 전체 테스트(이진, 종속성, 스크립트 등)를 업로드하여 패키지의 구성 요소를 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="80cb0-122">Tab 2 - Upload the components of your package by uploading a zip file with your entire test (binaries, dependencies, scripts etc).</span></span> 

<span data-ttu-id="80cb0-123">자세한 aka.ms/usl-package-outline 정보를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="80cb0-123">See aka.ms/usl-package-outline for details.</span></span> <span data-ttu-id="80cb0-124">참고: 첫 실행 테스트 스크립트와 기능 테스트 콘텐츠는 모두 동일한 zip 파일에 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="80cb0-124">(Note: Both the Out-of-Box test scripts and the Functional test contents should be placed into the same zip file).</span></span> <span data-ttu-id="80cb0-125">현재 파일 크기는 2GB로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="80cb0-125">Currently, the file size is limited to 2GB.</span></span>

<span data-ttu-id="80cb0-126">탭 3 - 기본 및 기능 테스트 작업을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="80cb0-126">Tab 3 - Configure the Out-of-Box and Functional test tasks.</span></span> <span data-ttu-id="80cb0-127">여기서 응용 프로그램을 설치, 실행, 닫기 및 제거하는 PowerShell 스크립트에 대한 경로와 모든 사용자 지정 스크립트에 대한 경로를 선택하고 기능 테스트를 수행하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="80cb0-127">Here, choose the path(s) to the PowerShell scripts that will install, launch, close, and uninstall your application (for Out-of-Box) as well as the path(s) to all your custom scripts to perform your functional test.</span></span> <span data-ttu-id="80cb0-128">**(참고: 응용 프로그램을 제거하기 위해 스크립트는 선택 사항입니다.**</span><span class="sxs-lookup"><span data-stu-id="80cb0-128">**(Note: A script to uninstall your application is optional).**</span></span>

<span data-ttu-id="80cb0-129">현재 기능 테스트를 위해 1~8개 스크립트를 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80cb0-129">Currently, you can upload between 1 and 8 scripts for your functional tests.</span></span> <span data-ttu-id="80cb0-130">(더 많은 스크립트가 필요한 경우 이 게시물에 대해 설명하세요!)</span><span class="sxs-lookup"><span data-stu-id="80cb0-130">(Kindly comment on this post if you need more scripts!)</span></span>

![업로드 테스트가 있는 스크립트 최대 8개](Media/functional_testing_tab3.png)

<span data-ttu-id="80cb0-132">(선택 사항) 설치 후 다시 시작을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="80cb0-132">(Optional) Configure a restart after installation.</span></span> <span data-ttu-id="80cb0-133">일부 응용 프로그램은 설치 후 다시 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="80cb0-133">Some applications require a restart after installation.</span></span> 

<span data-ttu-id="80cb0-134">해당 스크립트를 실행한 후 다시 시작을 수행하려면 작업 탭에서 특정 ```Reboot After Execution``` Script를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="80cb0-134">Select ```Reboot After Execution``` for the specific Script in the Tasks tab if you would like a restart to be conducted after the execution of that script.</span></span>

<span data-ttu-id="80cb0-135">탭 4 - Windows 업데이트가 설치되는 경우 선택: 원하는 스크립트를 Windows 업데이트 패치를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="80cb0-135">Tab 4 - Choose when the Windows update gets installed: The application of the Windows Update patch is done before any script of your choice.</span></span> <span data-ttu-id="80cb0-136">실제 응용 프로그램 사용 Windows 모방하기 위해 응용 프로그램을 설치한 후 업데이트를 설치하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="80cb0-136">It is recommended that you install a Windows update after the application's installation to closely mimic your real-world application use scenarios.</span></span>

![특정 Windows 업데이트가 설치될 수 있습니다.](Media/functional_testing_tab4.png)

<span data-ttu-id="80cb0-138">탭 5 - 패키지를 검토하고 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="80cb0-138">Tab 5 - Review and create the package.</span></span> <span data-ttu-id="80cb0-139">위에 나열된 단계를 완료한 후 업로드 프로세스를 ```Create``` 완료하려면 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="80cb0-139">Once you have completed the steps listed above, select ```Create``` to finish the uploading process.</span></span>

<span data-ttu-id="80cb0-140">패키지를 만든 후 패키지의 확인 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80cb0-140">Once your package has been created, you can check the verification status of your package.</span></span>

<span data-ttu-id="80cb0-141">응용 프로그램을 설치, 시작, 닫기 및 제거하기 위해 초기 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="80cb0-141">We run an initial test to install, launch, close, and uninstall your application.</span></span> <span data-ttu-id="80cb0-142">이를 통해 패키지가 오류 없는 서비스에 설치할 수 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80cb0-142">This allows us to verify that your package can install on our service error-free.</span></span>

<span data-ttu-id="80cb0-143">확인 프로세스는 최대 24시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80cb0-143">The verification process could take up to 24 hours.</span></span> <span data-ttu-id="80cb0-144">확인이 완료되면 메뉴에서 상태를 확인할 수 있습니다. 이 상태는 다음 두 항목 중 ```Manage packages``` 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80cb0-144">Once verification is complete, you can see the status in the ```Manage packages``` menu, which would be one of two entries:</span></span>

1. <span data-ttu-id="80cb0-145">확인 성공: 선택한 OS 빌드에 대한 Windows 시험판 업데이트에 대해 패키지가 자동으로 테스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="80cb0-145">Verification succeeds: The package will be automatically tested against pre-release Windows updates for the OS builds you selected.</span></span>
<span data-ttu-id="80cb0-146">또는</span><span class="sxs-lookup"><span data-stu-id="80cb0-146">or</span></span>
2. <span data-ttu-id="80cb0-147">확인 실패: 실패 이유를 조사하고 문제를 해결한 후 패키지를 다시 업로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="80cb0-147">Verification fails: You will need to investigate the reasons for the failure, fix the issue, and re-upload your package.</span></span>

<span data-ttu-id="80cb0-148">또한 Azure Portal의 알림 아이콘을 통해 두 결과 중 하나에 대한 알림을 하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80cb0-148">You will also be notified of either outcome via the notification icon in the Azure portal.</span></span>
