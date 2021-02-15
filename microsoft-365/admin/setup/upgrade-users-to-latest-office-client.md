---
title: Office 2010을 Microsoft 365로 업그레이드 - Microsoft 365 관리자
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
description: 조직의 사용자를 위해 Microsoft Office Office 클라이언트로 업그레이드하는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: 596dfc8f4a005d01c0bf330243bf1fb3c639f97e
ms.sourcegitcommit: 7355cc8871cde5fac6d7d6dcecc3e41e35601623
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2020
ms.locfileid: "48906444"
---
# <a name="upgrade-your-microsoft-365-for-business-users-to-the-latest-office-client"></a><span data-ttu-id="4d1c2-103">비즈니스용 Microsoft 365 사용자를 최신 Office 클라이언트로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="4d1c2-103">Upgrade your Microsoft 365 for business users to the latest Office client</span></span>

## <a name="office-2010-reaches-end-of-support"></a><span data-ttu-id="4d1c2-104">Office 2010 지원 종료</span><span class="sxs-lookup"><span data-stu-id="4d1c2-104">Office 2010 reaches end-of-support</span></span>

<span data-ttu-id="4d1c2-105">Office 2010은 2020년 10월 13일 지원이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d1c2-105">Office 2010 reached its end of support on October 13, 2020.</span></span> <span data-ttu-id="4d1c2-106">Microsoft는 더 이상 다음을 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4d1c2-106">Microsoft will no longer provide the following:</span></span>

- <span data-ttu-id="4d1c2-107">문제에 대한 기술 지원</span><span class="sxs-lookup"><span data-stu-id="4d1c2-107">Technical support for issues</span></span>

- <span data-ttu-id="4d1c2-108">발견된 문제에 대한 버그 수정</span><span class="sxs-lookup"><span data-stu-id="4d1c2-108">Bug fixes for issues that are discovered</span></span>

- <span data-ttu-id="4d1c2-109">발견된 취약점에 대한 보안 수정</span><span class="sxs-lookup"><span data-stu-id="4d1c2-109">Security fixes for vulnerabilities that are discovered</span></span>

<span data-ttu-id="4d1c2-110">자세한 [내용은 Office 2010](https://docs.microsoft.com/deployoffice/endofsupport/office-2010-end-support-roadmap) 지원 종료 로드맵을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4d1c2-110">See [Office 2010 end of support roadmap](https://docs.microsoft.com/deployoffice/endofsupport/office-2010-end-support-roadmap) for more information.</span></span>

 <span data-ttu-id="4d1c2-111">**이 항목은 적합한가요?**</span><span class="sxs-lookup"><span data-stu-id="4d1c2-111">**Is this the right topic for you?**</span></span>
  
 <span data-ttu-id="4d1c2-112">조직의 비즈니스용 Microsoft 365 구독을 담당하는 관리자인 경우 올바른 장소에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d1c2-112">If you're the admin responsible for the Microsoft 365 for business subscription in your organization, you're in the right place.</span></span> <span data-ttu-id="4d1c2-113">관리자는 일반적으로 사용자 관리, 암호 재설정, Office 설치 관리, 라이선스 추가 또는 제거와 같은 작업을 담당합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1c2-113">Admins are typically responsible for tasks like managing users, resetting passwords, managing Office installs and adding or removing licenses.</span></span>

 <span data-ttu-id="4d1c2-114">관리자가 아니며 [Microsoft 365](https://support.microsoft.com/office/28cbc8cf-1332-4f04-9123-9b660abb629e#BKMK_OfficePlans) 패밀리 제품이 있는 경우 이전 가정용 Office 버전을 업그레이드하는 방법에 대한 자세한 내용은 [Office를](https://support.microsoft.com/office/ee68f6cf-422f-464a-82ec-385f65391350) 업그레이드하는 방법을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4d1c2-114">If you're not an admin and you have a [Microsoft 365 Family](https://support.microsoft.com/office/28cbc8cf-1332-4f04-9123-9b660abb629e#BKMK_OfficePlans) product, see [How do I upgrade Office](https://support.microsoft.com/office/ee68f6cf-422f-464a-82ec-385f65391350) for information about upgrading your older, home use version of Office.</span></span>

## <a name="get-ready-to-upgrade-to-microsoft-365"></a><span data-ttu-id="4d1c2-115">Microsoft 365로 업그레이드 준비</span><span class="sxs-lookup"><span data-stu-id="4d1c2-115">Get ready to upgrade to Microsoft 365</span></span>

<span data-ttu-id="4d1c2-116">관리자는 조직의 사용자가 설치할 수 있는 Office 버전을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1c2-116">As an admin, you control what version of Office people in your organization can install.</span></span> <span data-ttu-id="4d1c2-117">조직의 사용자가 Office 2010, Office 2013 또는 Office 2016과 같은 이전 버전의 Office를 최신 버전으로 업그레이드하여 보안 및 생산성 향상을 활용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4d1c2-117">We highly recommend that you help users in your organization running older versions of Office such as Office 2010, Office 2013, or Office 2016 upgrade to the latest version to take advantage of its security and productivity improvements.</span></span>

## <a name="upgrade-steps"></a><span data-ttu-id="4d1c2-118">업그레이드 단계</span><span class="sxs-lookup"><span data-stu-id="4d1c2-118">Upgrade steps</span></span>

<span data-ttu-id="4d1c2-119">아래 단계에서는 사용자를 최신 Office 데스크톱 클라이언트로 업그레이드하는 프로세스를 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1c2-119">The steps below will guide you through the process of upgrading your users to the latest Office desktop client.</span></span> <span data-ttu-id="4d1c2-120">업그레이드 프로세스를 시작하기 전에 이러한 단계를 읽어보는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4d1c2-120">We recommend you read through these steps before beginning the upgrade process.</span></span>
  
## <a name="step-1---check-system-requirements"></a><span data-ttu-id="4d1c2-121">1단계 - 시스템 요구 사항 확인</span><span class="sxs-lookup"><span data-stu-id="4d1c2-121">Step 1 - Check system requirements</span></span>

<span data-ttu-id="4d1c2-122">[Office의 시스템](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources) 요구 사항을 확인하여 장치가 최신 버전의 Office와 호환되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1c2-122">[Check the system requirements](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources) for Office to make sure your devices are compatible with the latest version of Office.</span></span> <span data-ttu-id="4d1c2-123">예를 들어 최신 버전의 Office는 Windows XP 또는 Windows Vista를 실행하는 컴퓨터에 설치할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4d1c2-123">For example, newer versions of Office can't be installed on computers running Windows XP or Windows Vista.</span></span>
  
> [!TIP]
> <span data-ttu-id="4d1c2-124">조직의 사용자가 PC 또는 노트북에서 이전 버전의 Windows를 실행하는 경우 Windows 10으로 업그레이드하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4d1c2-124">If you have users in your organization running older versions of Windows on their PCs or laptops, we recommend upgrading to Windows 10.</span></span> <span data-ttu-id="4d1c2-125">Windows 7의 지원이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d1c2-125">Windows 7 has reached end of support.</span></span> <span data-ttu-id="4d1c2-126">자세한 [내용은 2020년 1월에 Windows 7에](https://www.microsoft.com/microsoft-365/windows/end-of-windows-7-support?rtc=1) 대한 지원이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d1c2-126">Read [Support for Windows 7 ends in January 2020](https://www.microsoft.com/microsoft-365/windows/end-of-windows-7-support?rtc=1) for more info.</span></span>

<span data-ttu-id="4d1c2-127">[Windows 10](https://www.microsoft.com/windows/windows-10-specifications) 시스템 요구 사항을 확인하여 운영 체제를 업그레이드할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1c2-127">Check out the [Windows 10 system requirements](https://www.microsoft.com/windows/windows-10-specifications) to see if you can upgrade their operating systems.</span></span>

### <a name="check-application-compatibility"></a><span data-ttu-id="4d1c2-128">응용 프로그램 호환성 확인</span><span class="sxs-lookup"><span data-stu-id="4d1c2-128">Check application compatibility</span></span>

<span data-ttu-id="4d1c2-129">업그레이드를 성공적으로 진행하려면 VBA 스크립트, 매크로, 타사 추가 기능, 복잡한 문서 및 스프레드시트를 비롯한 Office 응용 프로그램을 식별하고 최신 버전의 Office와의 호환성을 평가하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4d1c2-129">To ensure a successful upgrade, we recommend identifying your Office applications--including VBA scripts, macros, third-party add-ins, and complex documents and spreadsheets--and assessing their compatibility with the latest version of Office.</span></span>
  
<span data-ttu-id="4d1c2-130">예를 들어 현재 Office 설치에서 타사 추가 기능을 사용하는 경우 제조업체에 문의하여 최신 버전의 Office와 호환되는지를 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1c2-130">For example, if you're using third-party add-ins with your current Office install, contact the manufacture to make sure they're compatible with the latest version of Office.</span></span>
  
## <a name="step-2---check-your-existing-subscription-plan"></a><span data-ttu-id="4d1c2-131">2단계 - 기존 구독 계획 확인</span><span class="sxs-lookup"><span data-stu-id="4d1c2-131">Step 2 - Check your existing subscription plan</span></span>

<span data-ttu-id="4d1c2-132">일부 Microsoft 365 요금제에는 Office의 전체 데스크톱 버전이 포함되어 없습니다. 요금제에 Office가 포함되어하지 않는 경우 업그레이드 단계가 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="4d1c2-132">Some Microsoft 365 plans don't include the full desktop versions of Office and the steps to upgrade are different if your plan doesn't include Office.</span></span>
  
<span data-ttu-id="4d1c2-133">어떤 구독 요금제가 있는지 잘 모르겠나요?</span><span class="sxs-lookup"><span data-stu-id="4d1c2-133">Not sure which subscription plan you have?</span></span> <span data-ttu-id="4d1c2-134">비즈니스용 [Microsoft 365 구독에 대한 자세한 내용은 다음을 참조하세요.](../admin-overview/what-subscription-do-i-have.md)</span><span class="sxs-lookup"><span data-stu-id="4d1c2-134">See [What Microsoft 365 for business subscription do I have?](../admin-overview/what-subscription-do-i-have.md)</span></span>
  
<span data-ttu-id="4d1c2-135">기존 계획에 Office가 포함되어 있는 경우 [3단계 - Office 제거로 진행합니다.](#step-3---uninstall-office)</span><span class="sxs-lookup"><span data-stu-id="4d1c2-135">If your existing plan includes Office, move on to [Step 3 - Uninstall Office](#step-3---uninstall-office).</span></span>
  
<span data-ttu-id="4d1c2-136">기존 계획에 Office가 포함되어하지 않는 경우 아래 옵션에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1c2-136">If your existing plan doesn't include Office, then select from the options below:</span></span>
  
### <a name="upgrade-options-for-plans-that-dont-include-office"></a><span data-ttu-id="4d1c2-137">Office를 포함하지 않는 계획에 대한 업그레이드 옵션</span><span class="sxs-lookup"><span data-stu-id="4d1c2-137">Upgrade options for plans that don't include Office</span></span>

 <span data-ttu-id="4d1c2-138">**옵션 1: Office 구독 전환**</span><span class="sxs-lookup"><span data-stu-id="4d1c2-138">**Option 1: Switch Office subscriptions**</span></span>

<span data-ttu-id="4d1c2-139">Office를 포함하는 구독으로 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1c2-139">Switch to a subscription that includes Office.</span></span> <span data-ttu-id="4d1c2-140">다른 [비즈니스용 Microsoft 365 요금제로 전환을 참조합니다.](../../commerce/subscriptions/switch-to-a-different-plan.md)</span><span class="sxs-lookup"><span data-stu-id="4d1c2-140">See [Switch to a different Microsoft 365 for business plan](../../commerce/subscriptions/switch-to-a-different-plan.md).</span></span>

<span data-ttu-id="4d1c2-141">**옵션 2: Office의 개별, 일회성 구매 구입 또는 볼륨 라이선스를 통해 Office 구입**</span><span class="sxs-lookup"><span data-stu-id="4d1c2-141">**Option 2: Buy individual, one-time purchases of Office, or buy Office through a volume license**</span></span>

 - <span data-ttu-id="4d1c2-142">Office의 개인 일회성 구매를 구입합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1c2-142">Buy an individual, one-time purchase of Office.</span></span> <span data-ttu-id="4d1c2-143">[Office Home &amp; Business 또는](https://products.office.com/home-and-business) Office Professional [참조](https://products.office.com/professional)</span><span class="sxs-lookup"><span data-stu-id="4d1c2-143">See [Office Home &amp; Business](https://products.office.com/home-and-business) or [Office Professional](https://products.office.com/professional)</span></span>

     <span data-ttu-id="4d1c2-144">또는</span><span class="sxs-lookup"><span data-stu-id="4d1c2-144">OR</span></span>

 - <span data-ttu-id="4d1c2-145">볼륨 라이선스를 통해 여러 Office 복사본을 구입합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1c2-145">Buy multiple copies of Office through a volume license.</span></span> <span data-ttu-id="4d1c2-146">볼륨 [라이선싱을 통해 사용할 수 있는 제품군을 비교합니다.](https://products.office.com/business/microsoft-office-volume-licensing-suites-comparison)</span><span class="sxs-lookup"><span data-stu-id="4d1c2-146">See, [Compare suites available through volume licensing](https://products.office.com/business/microsoft-office-volume-licensing-suites-comparison).</span></span>

## <a name="step-3---uninstall-office"></a><span data-ttu-id="4d1c2-147">3단계 - Office 제거</span><span class="sxs-lookup"><span data-stu-id="4d1c2-147">Step 3 - Uninstall Office</span></span>

<span data-ttu-id="4d1c2-148">최신 버전의 Office를 설치하기 전에 이전 버전의 Office를 모두 제거하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4d1c2-148">Before installing the latest version of Office, we recommend you uninstall all older versions of Office.</span></span> <span data-ttu-id="4d1c2-149">그러나 Office 업그레이드에 대한 마음이 바뀌면 Office를 제거한 후 다시 설치하지 못하게 될 다음 인스턴스를 참고하십시오.</span><span class="sxs-lookup"><span data-stu-id="4d1c2-149">However, if you change your mind about upgrading Office, note the following instances where you won't be able to reinstall Office after uninstalling it.</span></span>
  
<span data-ttu-id="4d1c2-150">타사 추가 기능을 사용할 경우 제조업체에 문의하여 최신 버전의 Office에서 작동할 업데이트가 있는지 문의하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4d1c2-150">We recommend if you have third-party add-ins, contact the manufacturer to see if there's an update that will work with the latest version of Office.</span></span>

### <a name="select-the-version-of-office-you-want-to-uninstall"></a><span data-ttu-id="4d1c2-151">제거하려는 Office 버전 선택</span><span class="sxs-lookup"><span data-stu-id="4d1c2-151">Select the version of Office you want to uninstall</span></span>

- [<span data-ttu-id="4d1c2-152">PC에서</span><span class="sxs-lookup"><span data-stu-id="4d1c2-152">From a PC</span></span>](https://support.microsoft.com/office/9dd49b83-264a-477a-8fcc-2fdf5dbf61d8)

- [<span data-ttu-id="4d1c2-153">Mac에서</span><span class="sxs-lookup"><span data-stu-id="4d1c2-153">From a Mac</span></span>](https://support.microsoft.com/office/eefa1199-5b58-43af-8a3d-b73dc1a8cae3)
  
### <a name="known-issues-trying-to-reinstall-older-versions-of-office-after-an-uninstall"></a><span data-ttu-id="4d1c2-154">제거 후 이전 버전의 Office를 다시 설치하려는 알려진 문제</span><span class="sxs-lookup"><span data-stu-id="4d1c2-154">Known issues trying to reinstall older versions of Office after an uninstall</span></span>

 <span data-ttu-id="4d1c2-155">**볼륨 라이선스를 통한 Office** 이러한 볼륨 라이선스 버전의 Office의 원본 파일에 더 이상 액세스할 수 없는 경우 다시 설치하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1c2-155">**Office through a volume license** If you no longer have access to the source files of these volume license versions of Office, you won't be able to reinstall it.</span></span>

 <span data-ttu-id="4d1c2-156">**컴퓨터에 미리 설치된 Office** 디스크 또는 제품 키가 더 이상 없는 경우(Office에 제품 키가 있는 경우) 다시 설치하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1c2-156">**Office pre-installed on your computer** If you no longer have a disc or product key (if Office came with one) you won't be able to reinstall it.</span></span>

 <span data-ttu-id="4d1c2-157">**지원되지 않는 구독** Office 365 Small Business Premium 또는 Office 365 Mid-Size Business와 같은 중단된 구독을 통해 Office 복사본을 얻은 경우 구독과 함께 제공된 제품 키가 없는 경우 이전 버전의 Office를 설치할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4d1c2-157">**Non-supported subscriptions** If your copy of Office was obtained through discontinued subscriptions, such as Office 365 Small Business Premium or Office 365 Mid-size Business, you won't be able to install an older version of Office unless you have the product key that came with your subscription.</span></span>

<span data-ttu-id="4d1c2-158">이전 버전의 Office를 최신 버전과 나란히 설치하려면 이 버전이 지원되는 버전 목록을 볼 수 있으며, 동일한 [PC에서 다른 버전의 Office를](https://support.microsoft.com/office/6ebb44ce-18a3-43f9-a187-b78c513788bf)설치 및 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d1c2-158">If you'd prefer to install your older version of Office side-by-side with the latest version, you can see a list of versions where this is supported in, [Install and use different versions of Office on the same PC](https://support.microsoft.com/office/6ebb44ce-18a3-43f9-a187-b78c513788bf).</span></span> <span data-ttu-id="4d1c2-159">예를 들어 이전 버전의 Office와 함께 사용하는 타사 추가 기능을 설치한 경우 최신 버전과 호환되는지 아직 확실하지 않은 경우 함께 설치하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4d1c2-159">A side-by-side installation might be the right choice for you, if for example, you've installed third-party add-ins you're using with your older version of Office and you're not yet sure they're compatible with the latest version.</span></span>

## <a name="step-4---assign-office-licenses-to-users"></a><span data-ttu-id="4d1c2-160">4단계 - 사용자에게 Office 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="4d1c2-160">Step 4 - Assign Office licenses to users</span></span>

<span data-ttu-id="4d1c2-161">아직 Office를 설치해야 하는 조직의 사용자에게 라이선스를 할당하지 않은 경우 [비즈니스용 Microsoft 365의](../manage/assign-licenses-to-users.md)사용자에게 라이선스 할당을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1c2-161">If you haven't already done so, assign licenses to any users in your organization who need to install Office, see [Assign licenses to users in Microsoft 365 for business](../manage/assign-licenses-to-users.md).</span></span>
  
## <a name="step-5---install-office"></a><span data-ttu-id="4d1c2-162">5단계 - Office 설치</span><span class="sxs-lookup"><span data-stu-id="4d1c2-162">Step 5 - Install Office</span></span>

<span data-ttu-id="4d1c2-163">라이선스가 있는 모든 사용자를 업그레이드하려는 사용자를 확인한 후 마지막 단계는 Office를 설치하도록 하는 것입니다. PC 또는 Mac에 Office 다운로드 및 설치 또는 다시 설치를 [참조합니다.](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)</span><span class="sxs-lookup"><span data-stu-id="4d1c2-163">After you've verified the users you want to upgrade all have licenses, the final step is to have them install Office, see [Download and install or reinstall Office on your PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658).</span></span>
  
> [!TIP]
> <span data-ttu-id="4d1c2-164">사용자가 직접 Office를 설치하지 못하게 하려는 경우 [Office 365에서](https://docs.microsoft.com/DeployOffice/manage-software-download-settings-office-365)소프트웨어 다운로드 설정 관리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4d1c2-164">If you don't want your users installing Office themselves, see [Manage software download settings in Office 365](https://docs.microsoft.com/DeployOffice/manage-software-download-settings-office-365).</span></span> <span data-ttu-id="4d1c2-165">Office 배포 [도구를](https://docs.microsoft.com/DeployOffice/overview-office-deployment-tool) 사용하여 Office 소프트웨어를 로컬 네트워크에 다운로드한 다음 일반적으로 사용하는 소프트웨어 배포 방법을 사용하여 Office를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d1c2-165">You can use the [Office Deployment Tool](https://docs.microsoft.com/DeployOffice/overview-office-deployment-tool) to download the Office software to your local network and then deploy Office by using the software deployment method you typically use.</span></span>
