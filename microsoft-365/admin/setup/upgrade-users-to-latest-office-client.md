---
title: 비즈니스 사용자를 위한 Microsoft 365를 최신 Office 클라이언트로 업그레이드
f1.keywords:
- NOCSH
ms.author: kwekuako
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
- fwlink 824861; CampaignID O365_Comm_SR_UpgradeOffice
- AdminSurgePortfolio
ms.assetid: f6b00895-b5fd-4af6-a656-b7788ea20cbb
description: 사용자를 최신 Office 클라이언트로 업그레이드 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 22fe8e12e4aff4f9afe52e913ad57d37866dbb95
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44398813"
---
# <a name="upgrade-your-microsoft-365-for-business-users-to-the-latest-office-client"></a><span data-ttu-id="bf286-103">비즈니스 사용자를 위한 Microsoft 365를 최신 Office 클라이언트로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="bf286-103">Upgrade your Microsoft 365 for business users to the latest Office client</span></span>

## <a name="office-2010-reaches-end-of-support"></a><span data-ttu-id="bf286-104">Office 2010가 지원 끝에 도달 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf286-104">Office 2010 reaches end-of-support</span></span>

<span data-ttu-id="bf286-105">Office 2010는 2020 년 10 월 13 일에 지원 종료에 도달 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf286-105">Office 2010 will reach its end of support on October 13, 2020.</span></span> <span data-ttu-id="bf286-106">Office 2010가 지원 종료에 도달 하면 Microsoft는 더 이상 다음을 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bf286-106">When Office 2010 reaches its end of support, Microsoft will no longer provide the following:</span></span>

- <span data-ttu-id="bf286-107">문제에 대 한 기술 지원</span><span class="sxs-lookup"><span data-stu-id="bf286-107">Technical support for issues</span></span>

- <span data-ttu-id="bf286-108">발견 된 문제에 대 한 버그 수정 사항</span><span class="sxs-lookup"><span data-stu-id="bf286-108">Bug fixes for issues that are discovered</span></span>

- <span data-ttu-id="bf286-109">검색 된 취약성에 대 한 보안 수정 프로그램</span><span class="sxs-lookup"><span data-stu-id="bf286-109">Security fixes for vulnerabilities that are discovered</span></span>

<span data-ttu-id="bf286-110">자세한 내용은 [Office 2010 지원 센터의 최종 로드맵을](https://docs.microsoft.com/deployoffice/office-2010-end-support-roadmap) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bf286-110">See [Office 2010 end of support roadmap](https://docs.microsoft.com/deployoffice/office-2010-end-support-roadmap) for more information.</span></span>

 <span data-ttu-id="bf286-111">**이 항목이 적합 한 주제 입니까?**</span><span class="sxs-lookup"><span data-stu-id="bf286-111">**Is this the right topic for you?**</span></span>
  
 <span data-ttu-id="bf286-112">조직의 Microsoft 365 for business 구독을 담당 하는 관리자 인 경우 올바른 위치에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf286-112">If you're the admin responsible for the Microsoft 365 for business subscription in your organization, you're in the right place.</span></span> <span data-ttu-id="bf286-113">관리자는 일반적으로 사용자 관리, 암호 다시 설정, Office 설치 관리, 라이선스 추가 또는 제거와 같은 작업을 담당 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf286-113">Admins are typically responsible for tasks like managing users, resetting passwords, managing Office installs and adding or removing licenses.</span></span>

 <span data-ttu-id="bf286-114">관리자가 아닌 경우 [Microsoft 365](https://support.office.com/article/28cbc8cf-1332-4f04-9123-9b660abb629e.aspx#BKMK_OfficePlans) 제품을 사용 하는 경우 office 업그레이드에 대 한 자세한 내용을 확인 [하는 방법을](https://support.office.com/article/ee68f6cf-422f-464a-82ec-385f65391350.aspx) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bf286-114">If you're not an admin and you have a [Microsoft 365 Family](https://support.office.com/article/28cbc8cf-1332-4f04-9123-9b660abb629e.aspx#BKMK_OfficePlans) product, see [How do I upgrade Office](https://support.office.com/article/ee68f6cf-422f-464a-82ec-385f65391350.aspx) for information about upgrading your older, home use version of Office.</span></span>

## <a name="get-ready-to-upgrade"></a><span data-ttu-id="bf286-115">업그레이드 준비</span><span class="sxs-lookup"><span data-stu-id="bf286-115">Get ready to upgrade</span></span>

<span data-ttu-id="bf286-116">관리자는 조직에서 설치할 수 있는 Office 사용자의 버전을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf286-116">As an admin, you control what version of Office people in your organization can install.</span></span> <span data-ttu-id="bf286-117">조직의 사용자가 Office 2010, Office 2013 또는 Office 2016과 같은 이전 버전의 Office를 실행 하 여 보안 및 생산성 향상을 활용 하는 데 도움이 되도록 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bf286-117">We highly recommend that you help users in your organization running older versions of Office such as Office 2010, Office 2013, or Office 2016 upgrade to the latest version to take advantage of its security and productivity improvements.</span></span>

## <a name="upgrade-steps"></a><span data-ttu-id="bf286-118">업그레이드 단계</span><span class="sxs-lookup"><span data-stu-id="bf286-118">Upgrade steps</span></span>

<span data-ttu-id="bf286-119">아래 단계에서는 사용자를 최신 Office 데스크톱 클라이언트로 업그레이드 하는 프로세스를 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf286-119">The steps below will guide you through the process of upgrading your users to the latest Office desktop client.</span></span> <span data-ttu-id="bf286-120">업그레이드 프로세스를 시작 하기 전에 이러한 단계를 읽어 보는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bf286-120">We recommend you read through these steps before beginning the upgrade process.</span></span>
  
## <a name="step-1---check-system-requirements"></a><span data-ttu-id="bf286-121">1 단계-시스템 요구 사항 확인</span><span class="sxs-lookup"><span data-stu-id="bf286-121">Step 1 - Check system requirements</span></span>

<span data-ttu-id="bf286-122">Office의 [시스템 요구 사항을 확인](https://products.office.com/office-system-requirements) 하 여 장치가 최신 버전의 office와 호환 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf286-122">[Check the system requirements](https://products.office.com/office-system-requirements) for Office to make sure your devices are compatible with the latest version of Office.</span></span> <span data-ttu-id="bf286-123">예를 들어 Windows XP 또는 Windows Vista를 실행 하는 컴퓨터에 최신 버전의 Office를 설치할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bf286-123">For example, newer versions of Office can't be installed on computers running Windows XP or Windows Vista.</span></span>
  
> [!TIP]
> <span data-ttu-id="bf286-124">조직의 Pc 또는 랩톱에서 이전 버전의 Windows를 실행 하는 사용자가 있는 경우 Windows 10으로 업그레이드 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bf286-124">If you have users in your organization running older versions of Windows on their PCs or laptops, we recommend upgrading to Windows 10.</span></span> <span data-ttu-id="bf286-125">Windows 7이 지원 종료에 도달 했습니다.</span><span class="sxs-lookup"><span data-stu-id="bf286-125">Windows 7 has reached end of support.</span></span> <span data-ttu-id="bf286-126">자세한 내용은 [Windows 7에 대 한 읽기 지원이 1 월 2020 일에 끝납니다](https://www.microsoft.com/microsoft-365/windows/end-of-windows-7-support?rtc=1) .</span><span class="sxs-lookup"><span data-stu-id="bf286-126">Read [Support for Windows 7 ends in January 2020](https://www.microsoft.com/microsoft-365/windows/end-of-windows-7-support?rtc=1) for more info.</span></span>

<span data-ttu-id="bf286-127">[Windows 10 시스템 요구 사항을](https://www.microsoft.com/windows/windows-10-specifications) 확인 하 여 운영 체제를 업그레이드할 수 있는지 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="bf286-127">Check out the [Windows 10 system requirements](https://www.microsoft.com/windows/windows-10-specifications) to see if you can upgrade their operating systems.</span></span>

### <a name="check-application-compatibility"></a><span data-ttu-id="bf286-128">응용 프로그램 호환성 검사</span><span class="sxs-lookup"><span data-stu-id="bf286-128">Check application compatibility</span></span>

<span data-ttu-id="bf286-129">성공적인 업그레이드를 위해서는 VBA 스크립트, 매크로, 타사 추가 기능 및 복잡 한 문서와 스프레드시트를 비롯 하 여 Office 응용 프로그램을 확인 하 고 최신 버전의 Office와의 호환성을 평가 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bf286-129">To ensure a successful upgrade, we recommend identifying your Office applications--including VBA scripts, macros, third-party add-ins, and complex documents and spreadsheets--and assessing their compatibility with the latest version of Office.</span></span>
  
<span data-ttu-id="bf286-130">예를 들어 현재 Office 설치와 함께 타사 추가 기능을 사용 하는 경우 제조업체에 문의 하 여 최신 버전의 Office와 호환 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf286-130">For example, if you're using third-party add-ins with your current Office install, contact the manufacture to make sure they're compatible with the latest version of Office.</span></span>
  
## <a name="step-2---check-your-existing-subscription-plan"></a><span data-ttu-id="bf286-131">2 단계-기존 구독 계획 확인</span><span class="sxs-lookup"><span data-stu-id="bf286-131">Step 2 - Check your existing subscription plan</span></span>

<span data-ttu-id="bf286-132">일부 Microsoft 365 계획에는 전체 데스크톱 버전의 Office가 포함 되지 않으며 계획에 Office가 포함 되지 않은 경우 업그레이드 단계가 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="bf286-132">Some Microsoft 365 plans don't include the full desktop versions of Office and the steps to upgrade are different if your plan doesn't include Office.</span></span>
  
<span data-ttu-id="bf286-133">보유 하 고 있는 구독 계획을 확실히 알 수 없습니까?</span><span class="sxs-lookup"><span data-stu-id="bf286-133">Not sure which subscription plan you have?</span></span> <span data-ttu-id="bf286-134">[어떤 Microsoft 비즈니스 365 for business 구독이](../admin-overview/what-subscription-do-i-have.md) 있는지 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="bf286-134">See [What Microsoft 365 for business subscription do I have?](../admin-overview/what-subscription-do-i-have.md)</span></span>
  
<span data-ttu-id="bf286-135">기존 계획에 Office가 포함 되어 있는 경우 [3 단계-Office 제거](#step-3---uninstall-office)로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf286-135">If your existing plan includes Office, move on to [Step 3 - Uninstall Office](#step-3---uninstall-office).</span></span>
  
<span data-ttu-id="bf286-136">기존 계획에 Office가 포함 되어 있지 않은 경우 아래 옵션 중에서 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf286-136">If your existing plan doesn't include Office, then select from the options below:</span></span>
  
### <a name="upgrade-options-for-plans-that-dont-include-office"></a><span data-ttu-id="bf286-137">Office를 포함 하지 않는 요금제 업그레이드 옵션</span><span class="sxs-lookup"><span data-stu-id="bf286-137">Upgrade options for plans that don't include Office</span></span>

 <span data-ttu-id="bf286-138">**옵션 1: Office 구독 전환**</span><span class="sxs-lookup"><span data-stu-id="bf286-138">**Option 1: Switch Office subscriptions**</span></span>

<span data-ttu-id="bf286-139">Office를 포함 하는 구독으로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf286-139">Switch to a subscription that includes Office.</span></span> <span data-ttu-id="bf286-140">[다른 Microsoft 365 for business 요금제로 전환을](../../commerce/subscriptions/switch-to-a-different-plan.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bf286-140">See [Switch to a different Microsoft 365 for business plan](../../commerce/subscriptions/switch-to-a-different-plan.md).</span></span>

<span data-ttu-id="bf286-141">**옵션 2: 개별 Office 구매 구매 또는 볼륨 라이선스를 통해 Office 구입**</span><span class="sxs-lookup"><span data-stu-id="bf286-141">**Option 2: Buy individual, one-time purchases of Office, or buy Office through a volume license**</span></span>

 - <span data-ttu-id="bf286-142">Office의 개별 일회성 구매를 구매 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf286-142">Buy an individual, one-time purchase of Office.</span></span> <span data-ttu-id="bf286-143">[Office Home &amp; Business](https://products.office.com/home-and-business) 또는 [office Professional](https://products.office.com/professional) 참조</span><span class="sxs-lookup"><span data-stu-id="bf286-143">See [Office Home &amp; Business](https://products.office.com/home-and-business) or [Office Professional](https://products.office.com/professional)</span></span>

     <span data-ttu-id="bf286-144">또는</span><span class="sxs-lookup"><span data-stu-id="bf286-144">OR</span></span>

 - <span data-ttu-id="bf286-145">볼륨 라이선스를 통해 여러 Office 복사본을 구입 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf286-145">Buy multiple copies of Office through a volume license.</span></span> <span data-ttu-id="bf286-146">[볼륨 라이선스를 통해 사용할 수 있는 제품군 비교](https://products.office.com/business/microsoft-office-volume-licensing-suites-comparison)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bf286-146">See, [Compare suites available through volume licensing](https://products.office.com/business/microsoft-office-volume-licensing-suites-comparison).</span></span>

## <a name="step-3---uninstall-office"></a><span data-ttu-id="bf286-147">3 단계-Office 제거</span><span class="sxs-lookup"><span data-stu-id="bf286-147">Step 3 - Uninstall Office</span></span>

<span data-ttu-id="bf286-148">최신 버전의 Office를 설치 하기 전에 이전 버전의 Office를 모두 제거 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bf286-148">Before installing the latest version of Office, we recommend you uninstall all older versions of Office.</span></span> <span data-ttu-id="bf286-149">그러나 Office를 업그레이드 하는 방법에 대 한 생각이 변경 되는 경우에는 다음에 Office를 제거한 후 다시 설치할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf286-149">However, if you change your mind about upgrading Office, note the following instances where you won't be able to reinstall Office after uninstalling it.</span></span>
  
<span data-ttu-id="bf286-150">타사 추가 기능을 사용 하는 경우 제조업체에 문의 하 여 최신 버전의 Office에서 작동 하는 업데이트가 있는지 확인 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bf286-150">We recommend if you have third-party add-ins, contact the manufacturer to see if there's an update that will work with the latest version of Office.</span></span>

### <a name="select-the-version-of-office-you-want-to-uninstall"></a><span data-ttu-id="bf286-151">제거 하려는 Office 버전을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf286-151">Select the version of Office you want to uninstall</span></span>

- [<span data-ttu-id="bf286-152">PC에서</span><span class="sxs-lookup"><span data-stu-id="bf286-152">From a PC</span></span>](https://support.office.com/article/9dd49b83-264a-477a-8fcc-2fdf5dbf61d8.aspx)

- [<span data-ttu-id="bf286-153">Mac에서</span><span class="sxs-lookup"><span data-stu-id="bf286-153">From a Mac</span></span>](https://support.office.com/article/eefa1199-5b58-43af-8a3d-b73dc1a8cae3.aspx)
  
### <a name="known-issues-trying-to-reinstall-older-versions-of-office-after-an-uninstall"></a><span data-ttu-id="bf286-154">제거 후 이전 버전의 Office를 다시 설치 하려고 할 때의 알려진 문제</span><span class="sxs-lookup"><span data-stu-id="bf286-154">Known issues trying to reinstall older versions of Office after an uninstall</span></span>

 <span data-ttu-id="bf286-155">**볼륨 라이선스를 통해 Office 사용** 이러한 볼륨 라이선스 버전의 Office에 대 한 액세스 권한이 더 이상 없는 경우에는 다시 설치할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf286-155">**Office through a volume license** If you no longer have access to the source files of these volume license versions of Office, you won't be able to reinstall it.</span></span>

 <span data-ttu-id="bf286-156">**컴퓨터에 미리 설치 된 Office** 디스크 또는 제품 키가 더 이상 없는 경우에는 Office를 다시 설치할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf286-156">**Office pre-installed on your computer** If you no longer have a disc or product key (if Office came with one) you won't be able to reinstall it.</span></span>

 <span data-ttu-id="bf286-157">**지원 되지 않는 구독** Office 365 Small Business Premium 또는 Office 365 중간급 기업과 같이 단종 된 구독을 통해 Office 복사본을 구입한 경우 구독에 제공 된 제품 키가 없으면 이전 버전의 Office를 설치할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf286-157">**Non-supported subscriptions** If your copy of Office was obtained through discontinued subscriptions, such as Office 365 Small Business Premium or Office 365 Mid-size Business, you won't be able to install an older version of Office unless you have the product key that came with your subscription.</span></span>

<span data-ttu-id="bf286-158">최신 버전을 사용 하 여 이전 버전의 Office를 설치 하려는 경우에는이 기능이 지원 되는 버전 목록을 확인 하 고 [동일한 PC에 다른 버전의 Office를 설치 하 고 사용할](https://support.office.com/article/6ebb44ce-18a3-43f9-a187-b78c513788bf.aspx)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf286-158">If you'd prefer to install your older version of Office side-by-side with the latest version, you can see a list of versions where this is supported in, [Install and use different versions of Office on the same PC](https://support.office.com/article/6ebb44ce-18a3-43f9-a187-b78c513788bf.aspx).</span></span> <span data-ttu-id="bf286-159">예를 들어 이전 버전의 Office에서 사용 중인 타사 추가 기능을 설치한 경우 아직 최신 버전과 호환 되지 않는 경우에는 side-by-side 설치를 선택 하는 것이 적절 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf286-159">A side-by-side installation might be the right choice for you, if for example, you've installed third-party add-ins you're using with your older version of Office and you're not yet sure they're compatible with the latest version.</span></span>

## <a name="step-4---assign-office-licenses-to-users"></a><span data-ttu-id="bf286-160">4 단계-사용자에 게 Office 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="bf286-160">Step 4 - Assign Office licenses to users</span></span>

<span data-ttu-id="bf286-161">Office를 설치 해야 하는 조직의 모든 사용자에 게 라이선스를 할당 하지 않은 경우 [비즈니스에 대 한 Microsoft 365의 사용자에 게 라이선스 할당](../manage/assign-licenses-to-users.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bf286-161">If you haven't already done so, assign licenses to any users in your organization who need to install Office, see [Assign licenses to users in Microsoft 365 for business](../manage/assign-licenses-to-users.md).</span></span>
  
## <a name="step-5---install-office"></a><span data-ttu-id="bf286-162">5 단계-Office 설치</span><span class="sxs-lookup"><span data-stu-id="bf286-162">Step 5 - Install Office</span></span>

<span data-ttu-id="bf286-163">모든 사용자에 게 라이선스를 업그레이드할지 확인 한 후에는 [PC 또는 Mac에 office를 설치 하거나 다운로드 및 설치 또는 다시](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658.aspx)설치를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bf286-163">After you've verified the users you want to upgrade all have licenses, the final step is to have them install Office, see [Download and install or reinstall Office on your PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658.aspx).</span></span>
  
> [!TIP]
> <span data-ttu-id="bf286-164">사용자가 Office를 설치 하지 못하도록 하려면 [office 365에서 소프트웨어 다운로드 설정 관리](https://docs.microsoft.com/DeployOffice/manage-software-download-settings-office-365)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bf286-164">If you don't want your users installing Office themselves, see [Manage software download settings in Office 365](https://docs.microsoft.com/DeployOffice/manage-software-download-settings-office-365).</span></span> <span data-ttu-id="bf286-165">[Office 배포 도구](https://docs.microsoft.com/DeployOffice/overview-office-deployment-tool) 를 사용 하 여 로컬 네트워크에 office 소프트웨어를 다운로드 한 다음 일반적으로 사용 하는 소프트웨어 배포 방법을 사용 하 여 office를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf286-165">You can use the [Office Deployment Tool](https://docs.microsoft.com/DeployOffice/overview-office-deployment-tool) to download the Office software to your local network and then deploy Office by using the software deployment method you typically use.</span></span>
