---
title: Office 2010을 Microsoft 365 - Microsoft 365 관리자로 업그레이드
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.custom:
- fwlink 824861; CampaignID
- O365_Comm_SR_UpgradeOffice
- seo-marvel-may2020
- fwlink 824861; CampaignID O365_Comm_SR_UpgradeOffice
- AdminSurgePortfolio
ms.assetid: f6b00895-b5fd-4af6-a656-b7788ea20cbb
description: 조직의 사용자를 위한 최신 Microsoft Office 클라이언트로 업그레이드하는 Office 대해 자세히 알아보습니다.
ms.topic: article
ms.openlocfilehash: 877659e420079ed607adc13e5bbe44bdc979f5ac
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924698"
---
# <a name="upgrade-your-microsoft-365-for-business-users-to-the-latest-office-client"></a><span data-ttu-id="d5f8e-103">비즈니스 Microsoft 365 사용자를 최신 클라이언트로 업그레이드 Office 업그레이드</span><span class="sxs-lookup"><span data-stu-id="d5f8e-103">Upgrade your Microsoft 365 for business users to the latest Office client</span></span>

## <a name="office-2010-reaches-end-of-support"></a><span data-ttu-id="d5f8e-104">Office 2010이 지원 종료에 도달</span><span class="sxs-lookup"><span data-stu-id="d5f8e-104">Office 2010 reaches end-of-support</span></span>

<span data-ttu-id="d5f8e-105">Office 2010년 10월 13일 지원이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5f8e-105">Office 2010 reached its end of support on October 13, 2020.</span></span> <span data-ttu-id="d5f8e-106">Microsoft는 더 이상 다음을 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d5f8e-106">Microsoft will no longer provide the following:</span></span>

- <span data-ttu-id="d5f8e-107">문제에 대한 기술 지원</span><span class="sxs-lookup"><span data-stu-id="d5f8e-107">Technical support for issues</span></span>

- <span data-ttu-id="d5f8e-108">발견된 문제에 대한 버그 수정</span><span class="sxs-lookup"><span data-stu-id="d5f8e-108">Bug fixes for issues that are discovered</span></span>

- <span data-ttu-id="d5f8e-109">발견된 취약점에 대한 보안 수정</span><span class="sxs-lookup"><span data-stu-id="d5f8e-109">Security fixes for vulnerabilities that are discovered</span></span>

<span data-ttu-id="d5f8e-110">자세한 [Office 2010](/deployoffice/endofsupport/office-2010-end-support-roadmap) 지원 종료 로드맵을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d5f8e-110">See [Office 2010 end of support roadmap](/deployoffice/endofsupport/office-2010-end-support-roadmap) for more information.</span></span>

 <span data-ttu-id="d5f8e-111">**이것이 올바른 항목인가요?**</span><span class="sxs-lookup"><span data-stu-id="d5f8e-111">**Is this the right topic for you?**</span></span>
  
 <span data-ttu-id="d5f8e-112">조직에서 비즈니스용 구독을 Microsoft 365 관리자인 경우 올바른 장소에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5f8e-112">If you're the admin responsible for the Microsoft 365 for business subscription in your organization, you're in the right place.</span></span> <span data-ttu-id="d5f8e-113">관리자는 일반적으로 사용자 관리, 암호 재설정, 설치 관리, 라이선스 Office 제거와 같은 작업을 담당합니다.</span><span class="sxs-lookup"><span data-stu-id="d5f8e-113">Admins are typically responsible for tasks like managing users, resetting passwords, managing Office installs and adding or removing licenses.</span></span>

 <span data-ttu-id="d5f8e-114">관리자가 아니며 Microsoft 365 Family 제품을 사용하는 [](https://support.microsoft.com/office/28cbc8cf-1332-4f04-9123-9b660abb629e#BKMK_OfficePlans) 경우 이전 가정용 [](https://support.microsoft.com/office/ee68f6cf-422f-464a-82ec-385f65391350) 버전의 Office 업그레이드하는 방법에 대한 자세한 내용은 Office.</span><span class="sxs-lookup"><span data-stu-id="d5f8e-114">If you're not an admin and you have a [Microsoft 365 Family](https://support.microsoft.com/office/28cbc8cf-1332-4f04-9123-9b660abb629e#BKMK_OfficePlans) product, see [How do I upgrade Office](https://support.microsoft.com/office/ee68f6cf-422f-464a-82ec-385f65391350) for information about upgrading your older, home use version of Office.</span></span>

## <a name="get-ready-to-upgrade-to-microsoft-365"></a><span data-ttu-id="d5f8e-115">업그레이드할 준비를 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d5f8e-115">Get ready to upgrade to Microsoft 365</span></span>

<span data-ttu-id="d5f8e-116">관리자는 조직의 사용자가 설치할 수 있는 Office 버전을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="d5f8e-116">As an admin, you control what version of Office people in your organization can install.</span></span> <span data-ttu-id="d5f8e-117">조직의 사용자가 Office 2010, Office 2013 또는 Office 2016 업그레이드와 같은 이전 버전의 Office을 실행하는 조직의 사용자가 보안 및 생산성 향상을 활용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d5f8e-117">We highly recommend that you help users in your organization running older versions of Office such as Office 2010, Office 2013, or Office 2016 upgrade to the latest version to take advantage of its security and productivity improvements.</span></span>

## <a name="upgrade-steps"></a><span data-ttu-id="d5f8e-118">업그레이드 단계</span><span class="sxs-lookup"><span data-stu-id="d5f8e-118">Upgrade steps</span></span>

<span data-ttu-id="d5f8e-119">아래 단계에서는 사용자를 최신 데스크톱 클라이언트로 업그레이드하는 Office 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="d5f8e-119">The steps below will guide you through the process of upgrading your users to the latest Office desktop client.</span></span> <span data-ttu-id="d5f8e-120">업그레이드 프로세스를 시작하기 전에 이러한 단계를 읽어보는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d5f8e-120">We recommend you read through these steps before beginning the upgrade process.</span></span>
  
## <a name="step-1---check-system-requirements"></a><span data-ttu-id="d5f8e-121">1단계 - 시스템 요구 사항 확인</span><span class="sxs-lookup"><span data-stu-id="d5f8e-121">Step 1 - Check system requirements</span></span>

<span data-ttu-id="d5f8e-122">[장치의 시스템](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources) 요구 사항을 Office 최신 버전의 디바이스와 호환되는지 Office.</span><span class="sxs-lookup"><span data-stu-id="d5f8e-122">[Check the system requirements](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources) for Office to make sure your devices are compatible with the latest version of Office.</span></span> <span data-ttu-id="d5f8e-123">예를 들어 최신 버전의 Office XP 또는 Vista를 실행하는 컴퓨터에는 설치할 Windows Windows 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d5f8e-123">For example, newer versions of Office can't be installed on computers running Windows XP or Windows Vista.</span></span>
  
> [!TIP]
> <span data-ttu-id="d5f8e-124">조직의 사용자가 PC 또는 노트북에서 이전 버전의 Windows 실행하는 경우 이전 버전으로 업그레이드하는 Windows 10.</span><span class="sxs-lookup"><span data-stu-id="d5f8e-124">If you have users in your organization running older versions of Windows on their PCs or laptops, we recommend upgrading to Windows 10.</span></span> <span data-ttu-id="d5f8e-125">Windows 7이 지원 종료에 도달했습니다.</span><span class="sxs-lookup"><span data-stu-id="d5f8e-125">Windows 7 has reached end of support.</span></span> <span data-ttu-id="d5f8e-126">자세한 [내용은 Windows 2020년 1월 종료 7에](https://www.microsoft.com/microsoft-365/windows/end-of-windows-7-support?rtc=1) 대한 지원을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d5f8e-126">Read [Support for Windows 7 ends in January 2020](https://www.microsoft.com/microsoft-365/windows/end-of-windows-7-support?rtc=1) for more info.</span></span>

<span data-ttu-id="d5f8e-127">운영 [Windows 10 업그레이드할](https://www.microsoft.com/windows/windows-10-specifications) 수 있는지 확인하려면 시스템 요구 사항을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d5f8e-127">Check out the [Windows 10 system requirements](https://www.microsoft.com/windows/windows-10-specifications) to see if you can upgrade their operating systems.</span></span>

### <a name="check-application-compatibility"></a><span data-ttu-id="d5f8e-128">응용 프로그램 호환성 확인</span><span class="sxs-lookup"><span data-stu-id="d5f8e-128">Check application compatibility</span></span>

<span data-ttu-id="d5f8e-129">업그레이드를 성공적으로 진행하려면 VBA 스크립트, 매크로, 타사 추가 기능, 복잡한 문서 및 스프레드시트를 비롯한 Office 응용 프로그램을 식별하고 최신 버전의 Office.</span><span class="sxs-lookup"><span data-stu-id="d5f8e-129">To ensure a successful upgrade, we recommend identifying your Office applications--including VBA scripts, macros, third-party add-ins, and complex documents and spreadsheets--and assessing their compatibility with the latest version of Office.</span></span>
  
<span data-ttu-id="d5f8e-130">예를 들어 현재 설치 중인 타사 추가 기능을 Office 제조업체에 문의하여 최신 버전의 타사와 호환되는지 Office.</span><span class="sxs-lookup"><span data-stu-id="d5f8e-130">For example, if you're using third-party add-ins with your current Office install, contact the manufacture to make sure they're compatible with the latest version of Office.</span></span>
  
## <a name="step-2---check-your-existing-subscription-plan"></a><span data-ttu-id="d5f8e-131">2단계 - 기존 구독 계획 확인</span><span class="sxs-lookup"><span data-stu-id="d5f8e-131">Step 2 - Check your existing subscription plan</span></span>

<span data-ttu-id="d5f8e-132">일부 Microsoft 365 계획에는 전체 데스크톱 버전의 Office 계획에 포함되어하지 않는 경우 업그레이드 단계가 Office.</span><span class="sxs-lookup"><span data-stu-id="d5f8e-132">Some Microsoft 365 plans don't include the full desktop versions of Office and the steps to upgrade are different if your plan doesn't include Office.</span></span>
  
<span data-ttu-id="d5f8e-133">어떤 구독 플랜이 있는지 잘 모르겠나요?</span><span class="sxs-lookup"><span data-stu-id="d5f8e-133">Not sure which subscription plan you have?</span></span> <span data-ttu-id="d5f8e-134">비즈니스용 [Microsoft 365 어떤 구독이 있나요?를 참조하세요.](../admin-overview/what-subscription-do-i-have.md)</span><span class="sxs-lookup"><span data-stu-id="d5f8e-134">See [What Microsoft 365 for business subscription do I have?](../admin-overview/what-subscription-do-i-have.md)</span></span>
  
<span data-ttu-id="d5f8e-135">기존 계획에 포함된 Office [3단계 -](#step-3---uninstall-office)제거를 Office.</span><span class="sxs-lookup"><span data-stu-id="d5f8e-135">If your existing plan includes Office, move on to [Step 3 - Uninstall Office](#step-3---uninstall-office).</span></span>
  
<span data-ttu-id="d5f8e-136">기존 요금제에 추가 Office 경우 아래 옵션에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d5f8e-136">If your existing plan doesn't include Office, then select from the options below:</span></span>
  
### <a name="upgrade-options-for-plans-that-dont-include-office"></a><span data-ttu-id="d5f8e-137">업그레이드 옵션을 포함하지 않는 계획에 대한 Office</span><span class="sxs-lookup"><span data-stu-id="d5f8e-137">Upgrade options for plans that don't include Office</span></span>

 <span data-ttu-id="d5f8e-138">**옵션 1: Office 전환**</span><span class="sxs-lookup"><span data-stu-id="d5f8e-138">**Option 1: Switch Office subscriptions**</span></span>

<span data-ttu-id="d5f8e-139">구독이 포함된 구독으로 Office.</span><span class="sxs-lookup"><span data-stu-id="d5f8e-139">Switch to a subscription that includes Office.</span></span> <span data-ttu-id="d5f8e-140">비즈니스용 [요금제의 다른 Microsoft 365 전환을 참조합니다.](../../commerce/subscriptions/switch-to-a-different-plan.md)</span><span class="sxs-lookup"><span data-stu-id="d5f8e-140">See [Switch to a different Microsoft 365 for business plan](../../commerce/subscriptions/switch-to-a-different-plan.md).</span></span>

<span data-ttu-id="d5f8e-141">**옵션 2: 볼륨 라이선스를 통해 개별 Office 일회성 구매 또는 Office 구입**</span><span class="sxs-lookup"><span data-stu-id="d5f8e-141">**Option 2: Buy individual, one-time purchases of Office, or buy Office through a volume license**</span></span>

 - <span data-ttu-id="d5f8e-142">개인용 일회성 구매 제품 구매를 Office.</span><span class="sxs-lookup"><span data-stu-id="d5f8e-142">Buy an individual, one-time purchase of Office.</span></span> <span data-ttu-id="d5f8e-143">홈 [Office &amp; 또는](https://www.microsoft.com/microsoft-365/buy/compare-all-microsoft-365-products-b) [Office Professional](https://www.microsoft.com/microsoft-365/p/office-professional-2019/CFQ7TTC0K7C5/)</span><span class="sxs-lookup"><span data-stu-id="d5f8e-143">See [Office Home &amp; Business](https://www.microsoft.com/microsoft-365/buy/compare-all-microsoft-365-products-b) or [Office Professional](https://www.microsoft.com/microsoft-365/p/office-professional-2019/CFQ7TTC0K7C5/)</span></span>

     <span data-ttu-id="d5f8e-144">또는</span><span class="sxs-lookup"><span data-stu-id="d5f8e-144">OR</span></span>

 - <span data-ttu-id="d5f8e-145">볼륨 라이선스를 통해 Office 복사본을 여러 개 구입합니다.</span><span class="sxs-lookup"><span data-stu-id="d5f8e-145">Buy multiple copies of Office through a volume license.</span></span> <span data-ttu-id="d5f8e-146">볼륨 [라이선싱을 통해 사용 가능한 제품군 비교를 참조합니다.](https://products.office.com/business/microsoft-office-volume-licensing-suites-comparison)</span><span class="sxs-lookup"><span data-stu-id="d5f8e-146">See, [Compare suites available through volume licensing](https://products.office.com/business/microsoft-office-volume-licensing-suites-comparison).</span></span>

## <a name="step-3---uninstall-office"></a><span data-ttu-id="d5f8e-147">3단계 - 제거 Office</span><span class="sxs-lookup"><span data-stu-id="d5f8e-147">Step 3 - Uninstall Office</span></span>

<span data-ttu-id="d5f8e-148">최신 버전의 Office 설치하기 전에 이전 버전의 모든 이전 버전을 Office.</span><span class="sxs-lookup"><span data-stu-id="d5f8e-148">Before installing the latest version of Office, we recommend you uninstall all older versions of Office.</span></span> <span data-ttu-id="d5f8e-149">그러나 업그레이드에 대해 Office 경우 제거한 후 다시 Office 수 없는 다음 인스턴스를 참고하십시오.</span><span class="sxs-lookup"><span data-stu-id="d5f8e-149">However, if you change your mind about upgrading Office, note the following instances where you won't be able to reinstall Office after uninstalling it.</span></span>
  
<span data-ttu-id="d5f8e-150">타사 추가 기능을 사용할 경우 제조업체에 문의하여 최신 버전의 추가 기능으로 작동할 업데이트가 Office.</span><span class="sxs-lookup"><span data-stu-id="d5f8e-150">We recommend if you have third-party add-ins, contact the manufacturer to see if there's an update that will work with the latest version of Office.</span></span>

> [!TIP]
> <span data-ttu-id="d5f8e-151">설치 프로그램을 제거하는 동안 문제가 Office Microsoft 지원 및 복구 도우미 도구를 사용하여 Microsoft Office [다운로드](https://go.microsoft.com/fwlink/?LinkID=2155008)및 실행을 지원 및 복구 도우미.</span><span class="sxs-lookup"><span data-stu-id="d5f8e-151">If you run into issues while uninstalling Office, you can use the Microsoft Support and Recovery Assistant tool to help you remove Office: [Download and run the Microsoft Support and Recovery Assistant](https://go.microsoft.com/fwlink/?LinkID=2155008).</span></span>

### <a name="select-the-version-of-office-you-want-to-uninstall"></a><span data-ttu-id="d5f8e-152">제거하려는 Office 버전 선택</span><span class="sxs-lookup"><span data-stu-id="d5f8e-152">Select the version of Office you want to uninstall</span></span>

- [<span data-ttu-id="d5f8e-153">PC에서</span><span class="sxs-lookup"><span data-stu-id="d5f8e-153">From a PC</span></span>](https://support.microsoft.com/office/9dd49b83-264a-477a-8fcc-2fdf5dbf61d8)

- [<span data-ttu-id="d5f8e-154">Mac에서</span><span class="sxs-lookup"><span data-stu-id="d5f8e-154">From a Mac</span></span>](https://support.microsoft.com/office/eefa1199-5b58-43af-8a3d-b73dc1a8cae3)
  
### <a name="known-issues-trying-to-reinstall-older-versions-of-office-after-an-uninstall"></a><span data-ttu-id="d5f8e-155">제거 후 이전 버전의 Office 시도하는 알려진 문제</span><span class="sxs-lookup"><span data-stu-id="d5f8e-155">Known issues trying to reinstall older versions of Office after an uninstall</span></span>

 <span data-ttu-id="d5f8e-156">**Office 라이선스를 통해 배포** 이러한 볼륨 라이선스 버전의 원본 파일에 더 이상 액세스할 수 Office 경우 다시 설치할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d5f8e-156">**Office through a volume license** If you no longer have access to the source files of these volume license versions of Office, you won't be able to reinstall it.</span></span>

 <span data-ttu-id="d5f8e-157">**Office 미리 설치되어 있는 경우** 디스크 또는 제품 키가 더 이상 없는 경우(Office 함께 사용할 경우) 다시 설치할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d5f8e-157">**Office pre-installed on your computer** If you no longer have a disc or product key (if Office came with one) you won't be able to reinstall it.</span></span>

 <span data-ttu-id="d5f8e-158">**지원되지 않는 구독** Office 또는 Office 365 Business와 같은 중단된 구독을 통해 Office 365 Small Business Premium 또는 Office 365 구독을 통해 다운로드한 경우 구독과 함께 제공된 제품 키가 없는 경우 이전 버전의 Office 버전을 설치할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d5f8e-158">**Non-supported subscriptions** If your copy of Office was obtained through discontinued subscriptions, such as Office 365 Small Business Premium or Office 365 Mid-size Business, you won't be able to install an older version of Office unless you have the product key that came with your subscription.</span></span>

<span data-ttu-id="d5f8e-159">이전 버전의 Office 최신 버전과 함께 설치하려면 동일한 PC에 다른 버전의 Office 설치 및 사용에서 지원되는 버전 목록을 볼 수 [있습니다.](https://support.microsoft.com/office/6ebb44ce-18a3-43f9-a187-b78c513788bf)</span><span class="sxs-lookup"><span data-stu-id="d5f8e-159">If you'd prefer to install your older version of Office side-by-side with the latest version, you can see a list of versions where this is supported in, [Install and use different versions of Office on the same PC](https://support.microsoft.com/office/6ebb44ce-18a3-43f9-a187-b78c513788bf).</span></span> <span data-ttu-id="d5f8e-160">예를 들어 이전 버전의 Office 함께 사용하는 타사 추가 기능을 설치하고 최신 버전과 호환되는지 아직 확실하지 않은 경우를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5f8e-160">A side-by-side installation might be the right choice for you, if for example, you've installed third-party add-ins you're using with your older version of Office and you're not yet sure they're compatible with the latest version.</span></span>

## <a name="step-4---assign-office-licenses-to-users"></a><span data-ttu-id="d5f8e-161">4단계 - 사용자에게 Office 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="d5f8e-161">Step 4 - Assign Office licenses to users</span></span>

<span data-ttu-id="d5f8e-162">아직 라이선스를 할당하지 않은 경우 조직에서 라이선스를 설치해야 하는 사용자에게 라이선스를 Office 비즈니스용 Microsoft 365 라이선스 할당을 [참조합니다.](../manage/assign-licenses-to-users.md)</span><span class="sxs-lookup"><span data-stu-id="d5f8e-162">If you haven't already done so, assign licenses to any users in your organization who need to install Office, see [Assign licenses to users in Microsoft 365 for business](../manage/assign-licenses-to-users.md).</span></span>
  
## <a name="step-5---install-office"></a><span data-ttu-id="d5f8e-163">5단계 - 설치 Office</span><span class="sxs-lookup"><span data-stu-id="d5f8e-163">Step 5 - Install Office</span></span>

<span data-ttu-id="d5f8e-164">모든 라이선스를 업그레이드하려는 사용자를 확인한 후 마지막 단계는 라이선스를 설치하도록 하는 것입니다Office PC 또는 [Mac에](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)Office 다운로드 및 설치 또는 다시 설치를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="d5f8e-164">After you've verified the users you want to upgrade all have licenses, the final step is to have them install Office, see [Download and install or reinstall Office on your PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658).</span></span>
  
> [!TIP]
> <span data-ttu-id="d5f8e-165">사용자가 직접 설치하지 못하게 Office 에서 소프트웨어 다운로드 설정 [관리를 Office 365.](/DeployOffice/manage-software-download-settings-office-365)</span><span class="sxs-lookup"><span data-stu-id="d5f8e-165">If you don't want your users installing Office themselves, see [Manage software download settings in Office 365](/DeployOffice/manage-software-download-settings-office-365).</span></span> <span data-ttu-id="d5f8e-166">Office [배포](/DeployOffice/overview-office-deployment-tool) 도구를 사용하여 Office 소프트웨어를 다운로드한 다음 일반적으로 사용하는 소프트웨어 배포 Office 사용하여 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5f8e-166">You can use the [Office Deployment Tool](/DeployOffice/overview-office-deployment-tool) to download the Office software to your local network and then deploy Office by using the software deployment method you typically use.</span></span>