---
title: 테스트 기본 FAQ
description: 자주 묻는 질문 검토
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: troubleshooting
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 9d24ecb807e60733471be60353d12789f19be1b4
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323382"
---
# <a name="test-base-faq"></a><span data-ttu-id="83d2c-103">테스트 기본 FAQ</span><span class="sxs-lookup"><span data-stu-id="83d2c-103">Test Base FAQ</span></span>

<span data-ttu-id="83d2c-104">**Q: 테스트 기반 팀에 패키지를 제출하는 방법**</span><span class="sxs-lookup"><span data-stu-id="83d2c-104">**Q: How do we submit our packages to Test Base team?**</span></span>

<span data-ttu-id="83d2c-105">**A:** 셀프 서비스 포털을 사용하여 테스트 기준 환경에 직접 패키지를 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="83d2c-105">**A:** Submit your packages directly to the Test Base environment using our self-serve portal.</span></span>

<span data-ttu-id="83d2c-106">응용 프로그램 패키지를 제출하려면 [Azure Portal로](https://www.aka.ms/testbaseportal "테스트 기본 홈페이지") 이동하여 셀프 서비스 테스트 기준 포털 대시보드를 통해 응용 프로그램의 이진, 종속성 및 테스트 스크립트가 포함된 압축된 폴더를 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="83d2c-106">To submit your application package, navigate to the [Azure Portal](https://www.aka.ms/testbaseportal "Test Base Homepage") and upload a zipped folder containing your application's binaries, dependencies, and test scripts via the self-serve Test Base portal dashboard.</span></span> 

<span data-ttu-id="83d2c-107">자세한 내용은 온보드 사용자 가이드를 참조하거나 지원 및 자세한 내용은 <testbasepreview@microsoft.com> 팀에 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="83d2c-107">Please see the onboarding user guide for more information or contact our team at <testbasepreview@microsoft.com> for assistance and more information.</span></span>

<span data-ttu-id="83d2c-108">**Q: OOB(Out-of-Box) 테스트는 무엇입니까?**</span><span class="sxs-lookup"><span data-stu-id="83d2c-108">**Q: What are Out-of-box (OOB) tests?**</span></span>

<span data-ttu-id="83d2c-109">**A:** OOB(기본 제공) 테스트는 표준화되어 있으며, 응용 프로그램 패키지가 설치, 시작 및 닫힌 후 30회(30회) 제거되는 기본 테스트가 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="83d2c-109">**A:** Out-of-box (OOB) tests are standardized, default test runs where application packages are installed, launched and closed thirty (30) times, and then uninstalled.</span></span> 

<span data-ttu-id="83d2c-110">Test Base를 위해 만든 패키지에는 설치, 실행, 닫기 및 선택적으로 제거 스크립트의 테스트 스크립트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83d2c-110">The packages created for Test Base will have the following test scripts: install, launch, close, and optionally the uninstall script.</span></span> 

<span data-ttu-id="83d2c-111">OOB(첫 실행) 테스트는 응용 프로그램에서 표준화된 원격 분석 기능을 제공하여 여러 빌드에서 Windows 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="83d2c-111">The Out-of-box (OOB) tests provide you with standardized telemetry on your application to compare across Windows builds.</span></span>

<span data-ttu-id="83d2c-112">**Q: 첫 실행 테스트(설치, 실행, 닫기, 제거 테스트 스크립트) 외부에서 테스트를 제출할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="83d2c-112">**Q: Can we submit tests outside of the Out-of-box tests (install, launch, close, uninstall test scripts)?**</span></span>

<span data-ttu-id="83d2c-113">**A:** 예, 고객은 셀프 서비스  포털 대시보드를 통해 기능 테스트용 응용 프로그램 패키지를 업로드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83d2c-113">**A:** Yes, customers can also upload application packages for **functional tests** via the self-serve portal dashboard.</span></span>
<span data-ttu-id="83d2c-114">**기능 테스트는** 고객이 스크립트를 실행하여 응용 프로그램에서 사용자 지정 기능을 실행할 수 있도록 하는 테스트입니다.</span><span class="sxs-lookup"><span data-stu-id="83d2c-114">**Functional tests** are tests that enable customers execute their scripts to run custom functionality on their application.</span></span>


## <a name="testing"></a><span data-ttu-id="83d2c-115">테스트</span><span class="sxs-lookup"><span data-stu-id="83d2c-115">Testing</span></span>

<span data-ttu-id="83d2c-116">**Q: 기능 테스트를 지원하나요?**</span><span class="sxs-lookup"><span data-stu-id="83d2c-116">**Q: Do you support functional tests?**</span></span>

<span data-ttu-id="83d2c-117">**A:** 예, Test Base는 기능 테스트를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="83d2c-117">**A:** Yes, Test Base supports functional tests.</span></span> <span data-ttu-id="83d2c-118">기능 테스트는 고객이 스크립트를 실행하여 응용 프로그램에서 사용자 지정 기능을 실행할 수 있도록 하는 테스트입니다.</span><span class="sxs-lookup"><span data-stu-id="83d2c-118">Functional tests are tests that enable our customers execute their scripts to run custom functionality on their application.</span></span> 

<span data-ttu-id="83d2c-119">기능 테스트를 위해 응용 프로그램 패키지를 제출하려면 셀프 서비스 포털 대시보드를 통해 응용 프로그램의 이진 파일, 종속성 및 테스트 스크립트가 포함된 압축된 폴더를 업로드하기만 합니다.</span><span class="sxs-lookup"><span data-stu-id="83d2c-119">To submit your application package for functional testing, simply upload the zipped folder containing your application's binaries, dependencies, and test scripts via our self-serve portal dashboard.</span></span> 

<span data-ttu-id="83d2c-120">자세한 내용은 온보드 사용자 가이드를 참조하거나 지원 및 자세한 내용은 <testbasepreview@microsoft.com> 팀에 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="83d2c-120">Please see the onboarding user guide for more information or contact our team at <testbasepreview@microsoft.com> for assistance and more information.</span></span>

<span data-ttu-id="83d2c-121">**Q: Test Base는 테스트 데이터를 어떻게 처리하나요?**</span><span class="sxs-lookup"><span data-stu-id="83d2c-121">**Q: How does Test Base handle our test data?**</span></span>

<span data-ttu-id="83d2c-122">**A:** 테스트 기준은 Azure 환경에서 테스트 데이터를 안전하게 수집하고 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="83d2c-122">**A:** Test Base securely collects and manages your test data on the Azure environment.</span></span> 

<span data-ttu-id="83d2c-123">**Q: 테스트 기준이 자동화된 테스트를 지원할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="83d2c-123">**Q: Can Test Base support our automated tests?**</span></span>

<span data-ttu-id="83d2c-124">예, Test Base는 자동화된 테스트를 지원하기는 하지만 현재는 서비스 기능으로 인해 수동 테스트를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83d2c-124">Yes, Test Base supports automated tests however, we do not support manual tests at this time due to service capabilities.</span></span>

<span data-ttu-id="83d2c-125">**Q: 지원할 자동화된 테스트의 언어 및 프레임워크는 무엇입니까?**</span><span class="sxs-lookup"><span data-stu-id="83d2c-125">**Q: What languages and frameworks of automated tests do you support?**</span></span>

<span data-ttu-id="83d2c-126">**A:** 모든 언어 및 프레임워크를 지원하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83d2c-126">**A:** We support all languages and frameworks.</span></span> <span data-ttu-id="83d2c-127">PowerShell을 통해 모든 스크립트를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="83d2c-127">We invoke all scripts through PowerShell.</span></span> 

<span data-ttu-id="83d2c-128">또한 필요한 프레임워크의 종속 이진 파일을 제공(업로드)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83d2c-128">You will also need to provide (upload) the dependent binaries of the required framework.</span></span>

<span data-ttu-id="83d2c-129">**Q: 테스트 기준에서 테스트 결과를 얼마나 빨리 제공하나요?**</span><span class="sxs-lookup"><span data-stu-id="83d2c-129">**Q: How soon does Test Base provide test results?**</span></span>

<span data-ttu-id="83d2c-130">**A:** 시험판 빌드에 대해 실행된 각 테스트에 대해 [Azure Portal](https://www.aka.ms/testbaseportal "테스트 기본 홈페이지") 대시보드에서 48시간 이내에 결과를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="83d2c-130">**A:** For each test that we run against the pre-release builds, we will provide results within 48 hours on your [Azure Portal](https://www.aka.ms/testbaseportal "Test Base Homepage") dashboard.</span></span>

<span data-ttu-id="83d2c-131">**Q: 설치 후 재부팅할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="83d2c-131">**Q: Can you reboot after install?**</span></span>

<span data-ttu-id="83d2c-132">**A:** 예, 설치 후 프로세스에서 재부팅을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="83d2c-132">**A:** Yes, our process supports rebooting after installation.</span></span> <span data-ttu-id="83d2c-133">온보드 포털에서 작업을 설정할 때 "선택적  설정" 드롭 목록에서 이 옵션을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83d2c-133">Be sure to select this option from the “Optional settings” drop list when setting your **Tasks** on the onboarding portal.</span></span>

<span data-ttu-id="83d2c-134">OOB(첫 실행) 테스트의 경우 설치 스크립트에 재부팅이 필요한지 _여부를 지정할 수 있습니다._</span><span class="sxs-lookup"><span data-stu-id="83d2c-134">For Out-of-box (OOB) tests, you can specify whether a reboot is needed for the _Install script._</span></span>

![사진 다시부팅](Media/reboot.png)

<span data-ttu-id="83d2c-136">기능 테스트의 경우 추가되는 각 스크립트에 대해 재부팅이 필요한지 여부를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83d2c-136">While for functional tests, you can specify whether a reboot is required for each script that is added.</span></span>

![기능 테스트를 선택하는 방법](Media/functionalreboot.png)

<span data-ttu-id="83d2c-138">**Q: Windows 버전은 무엇입니까?**</span><span class="sxs-lookup"><span data-stu-id="83d2c-138">**Q: What Windows versions do you support?**</span></span>

<span data-ttu-id="83d2c-139">**A:** 현재 Windows 10 클라이언트, Windows Server 2016, Windows Server 2016 Core 버전, Windows Server 2019 및 Windows Server 2019 Core 버전을 지원하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83d2c-139">**A:** We currently support Windows 10 clients, Windows Server 2016, Windows Server 2016 Core version, Windows Server 2019, and Windows Server 2019 Core version.</span></span>

<span data-ttu-id="83d2c-140">**Q: 보안 업데이트 테스트와 기능 업데이트 테스트의 차이점은 무엇입니까?**</span><span class="sxs-lookup"><span data-stu-id="83d2c-140">**Q: What is the difference between Security Update tests and Feature Update tests?**</span></span>

<span data-ttu-id="83d2c-141">**A:** 보안 업데이트 테스트의 경우 **<ins></ins>** 사용자를 항상 보호하고 보호하는 데 중점을 Windows 릴리스 전 보안 업데이트에 대해 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="83d2c-141">**A:** For Security update tests, we test against the **<ins>monthly pre-release security updates</ins>** on Windows which are focused on keeping our users always secure and protected.</span></span> <span data-ttu-id="83d2c-142">기능 업데이트 테스트에서는 새로운 기능을 **<ins></ins>** 소개하는 쌍회 시험판 기능 업데이트에 대해 테스트하여 Windows.</span><span class="sxs-lookup"><span data-stu-id="83d2c-142">For the Feature update tests, we test against the **<ins>bi-annual pre-release feature updates</ins>** which introduces new features and capabilities on Windows.</span></span>

## <a name="debugging-options"></a><span data-ttu-id="83d2c-143">디버깅 옵션</span><span class="sxs-lookup"><span data-stu-id="83d2c-143">Debugging options</span></span>

<span data-ttu-id="83d2c-144">**Q: 오류가 발생하면 VM(가상 컴퓨터)에 액세스할 수 있나요? 테스트 기준 공유는 어떻게 하나요?**</span><span class="sxs-lookup"><span data-stu-id="83d2c-144">**Q: Do we get access to the Virtual Machines (VMs) in case of failures? What does Test Base share?**</span></span>

<span data-ttu-id="83d2c-145">**A:** 서비스가 규정을 준수하고 사전 릴리스 업데이트의 보안을 유지하도록 하는 경우 Microsoft만 VM에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83d2c-145">**A:** For the service to be compliant and the pre-release updates be secure, only Microsoft has access to the VMs.</span></span> <span data-ttu-id="83d2c-146">그러나 고객은 크래시 및 중단 신호, 안정성 메트릭, 메모리 및 CPU 사용률 등 테스트 결과 및 기타 테스트 메트릭을 포털 대시보드에서 볼 수 있습니다. 또한 다운로드 및 추가 분석을 위해 대시보드에서 테스트 실행 로그를 생성하고 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="83d2c-146">However, customers can view test results and other test metrics on their portal dashboard, including crash and hang signals, reliability metrics, memory and CPU utilization etc. We also generate and provide logs of test runs on the dashboard for download and further analysis.</span></span> 

<span data-ttu-id="83d2c-147">필요한 경우 크래시 디버깅을 위한 메모리 덤프를 제공할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83d2c-147">We can also provide memory dumps for crash debugging as needed.</span></span>

<span data-ttu-id="83d2c-148">**Q: 테스트 중에 문제가 발견된 경우 이러한 문제를 해결하기 위한 다음 단계는 무엇입니까?**</span><span class="sxs-lookup"><span data-stu-id="83d2c-148">**Q: If there are issues found during the testing, what are the next steps to resolve these issues?**</span></span>

<span data-ttu-id="83d2c-149">**A:** 테스트 기반 팀은 초기의 판정 프로세스를 수행하여 오류의 근본 원인을 확인한 다음, 확인한 결과에 따라 디버깅을 위해 Microsoft 내의 고객 또는 내부 팀으로 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="83d2c-149">**A:** The Test Base team will perform an initial triage process to determine the root cause of the error, and then depending on our findings, we will route to the customer or internal teams within Microsoft for debugging.</span></span> 

<span data-ttu-id="83d2c-150">We always work closely with our customers in joint remediation to resolve any issues.</span><span class="sxs-lookup"><span data-stu-id="83d2c-150">We always work closely with our customers in joint remediation to resolve any issues.</span></span> 

<span data-ttu-id="83d2c-151">**Q: Microsoft는 문제가 해결될 때까지 보안 패치 릴리스를 보유하나요? 사용할 수 있는 대체 해결 방법**</span><span class="sxs-lookup"><span data-stu-id="83d2c-151">**Q: Does Microsoft hold the release of the security patch until the issue is resolved? What alternate resolutions are available?**</span></span>

<span data-ttu-id="83d2c-152">**A:** 테스트 기준의 목표는 공동 최종 고객이 문제에 직면하지 않도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="83d2c-152">**A:** The goal of Test Base is to ensure our joint end customers do not face any issues.</span></span> <span data-ttu-id="83d2c-153">We will work with Software Vendors to address any issues before the release, but in case the fix is notible we have other resolutions such as shims and blocks.</span><span class="sxs-lookup"><span data-stu-id="83d2c-153">We will work hard with Software Vendors to address any issues before the release, but in case the fix is not feasible we have other resolutions such as shims and blocks.</span></span>

## <a name="miscellaneous"></a><span data-ttu-id="83d2c-154">기타</span><span class="sxs-lookup"><span data-stu-id="83d2c-154">Miscellaneous</span></span>

<span data-ttu-id="83d2c-155">**Q: 서비스가 프레미스 서버에서 어떻게 작동하나요?**</span><span class="sxs-lookup"><span data-stu-id="83d2c-155">**Q: How will the service work with an on-prem server?**</span></span>

<span data-ttu-id="83d2c-156">**A:** 현재는 프레미스 서버가 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83d2c-156">**A:** We currently do not provide support for on-prem servers.</span></span> <span data-ttu-id="83d2c-157">그러나 서버에서 HTTP 끝점을 노출하는 경우 인터넷을 통해 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83d2c-157">However, if the server is exposing HTTP endpoint, we can connect to it over the internet.</span></span>

<span data-ttu-id="83d2c-158">**Q: Who VM을 호스트하나요?**</span><span class="sxs-lookup"><span data-stu-id="83d2c-158">**Q: Who hosts the VMs?**</span></span>

<span data-ttu-id="83d2c-159">**A:** Microsoft는 이 서비스에 대한 VM을 프로비전하여 고객의 부하를 가중합니다.</span><span class="sxs-lookup"><span data-stu-id="83d2c-159">**A:** Microsoft provisions the VM for this service, taking the load of doing so from the customer.</span></span>

<span data-ttu-id="83d2c-160">**Q: 이 서비스는 웹, 모바일 또는 데스크톱 응용 프로그램을 지원하나요?**</span><span class="sxs-lookup"><span data-stu-id="83d2c-160">**Q: Does this service support web, mobile, or desktop applications?**</span></span>

<span data-ttu-id="83d2c-161">**A:** 현재는 데스크톱 응용 프로그램에 초점을 맞추지만 향후 웹 응용 프로그램을 온보드할 계획이 있지만 현재 모바일 응용 프로그램은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83d2c-161">**A:** Currently, our focus is on desktop applications, however, we have plans to onboard web applications in the future, but we do not support mobile applications at this time.</span></span>

<span data-ttu-id="83d2c-162">**Q: 테스트 베이스와 SUVP의 차이점은 무엇입니까?**</span><span class="sxs-lookup"><span data-stu-id="83d2c-162">**Q: What is the difference between Test Base and SUVP?**</span></span>

<span data-ttu-id="83d2c-163">**A:** 테스트 기준과 SUVP의 가장 큰 차이점은 테스트 자체를 수행하지 않고 시험판 업데이트에 대해 유효성 검사를 위해 테스트 기반 Azure 환경에 응용 프로그램을 온보드하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="83d2c-163">**A:** The biggest difference between Test Base and SUVP is that our partners onboard their applications onto the Test Base Azure environment for validation runs against pre-release updates instead of carrying out the tests themselves.</span></span> 

<span data-ttu-id="83d2c-164">시험판 보안 업데이트 테스트 외에도 플랫폼에서 시험판 기능 업데이트 테스트를 지원하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83d2c-164">In addition to pre-release security updates testing, we support pre-release feature updates testing on our platform.</span></span> <span data-ttu-id="83d2c-165">로드맵에는 다른 유형의 업데이트 및 OS 테스트가 많이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83d2c-165">We have many other types of updates and OS testing on our roadmap.</span></span>

<span data-ttu-id="83d2c-166">**Q: 서비스 관련 비용이 있나요?**</span><span class="sxs-lookup"><span data-stu-id="83d2c-166">**Q: Is there a cost associated with the service?**</span></span>

<span data-ttu-id="83d2c-167">**A:** 테스트 기준 서비스는 GA(일반 공급)가 될 때까지 사용자에게 무료로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="83d2c-167">**A:** The Test Base service will be free to users until General Availability (GA).</span></span> <span data-ttu-id="83d2c-168">이때 모든 고객에게 적용될 비용 구조를 발표할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="83d2c-168">At that time, we will announce a cost structure that will be in effect for all customers.</span></span> 

<span data-ttu-id="83d2c-169">**Q: 테스트 기준에 대한 피드백을 제공하면 어떻게 하나요?**</span><span class="sxs-lookup"><span data-stu-id="83d2c-169">**Q: How can I provide feedback about Test Base?**</span></span>

<span data-ttu-id="83d2c-170">**A:** 테스트 기준에 대한 피드백을  공유하려면 포털 왼쪽 아래에 있는 피드백 아이콘을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="83d2c-170">**A:** To share your feedback about Test Base, select the **Feedback** icon at the bottom left of the portal.</span></span> <span data-ttu-id="83d2c-171">제출에 스크린샷을 포함하면 Microsoft에서 피드백을 더 잘 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83d2c-171">Include a screenshot with your submission to help Microsoft better understand your feedback.</span></span> 

<span data-ttu-id="83d2c-172">또한 에서 제품 제안을 제출하고 다른 아이디어를 지지할 수도 <testbasepreview@microsoft.com> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83d2c-172">You can also submit product suggestions and upvote other ideas at <testbasepreview@microsoft.com>.</span></span>
